# Adapter
permite que clases con interfaces incompatibles trabajen juntas. Actúa como un puente entre dos interfaces diferentes, adaptando una interfaz a otra que el cliente espera.
## Ejemplo:
Supongamos que tenemos un sistema de audio que espera objetos que implementen la interfaz **MediaPlayer**. Tenemos una clase existente **AudioPlayer** que implementa esta interfaz
y puede reproducir archivos de audio. También tenemos una nueva clase **AdvancedMediaPlayer** que puede reproducir archivos de video, pero no implementa **MediaPlayer**.
Utilizaremos el patrón Adapter para que **AdvancedMediaPlayer** pueda ser utilizado como **MediaPlayer**.
1. Definir las interfaces
```java
// Interfaz MediaPlayer
interface MediaPlayer {
    void play(String audioType, String fileName);
}

// Interfaz AdvancedMediaPlayer
interface AdvancedMediaPlayer {
    void playVlc(String fileName);
    void playMp4(String fileName);
}
```
2. Implementar las clases concretas
```java
// Implementación de AdvancedMediaPlayer para VLC
class VlcPlayer implements AdvancedMediaPlayer {
    @Override
    public void playVlc(String fileName) {
        System.out.println("Reproduciendo VLC archivo: " + fileName);
    }

    @Override
    public void playMp4(String fileName) {
        // No hacer nada
    }
}

// Implementación de AdvancedMediaPlayer para MP4
class Mp4Player implements AdvancedMediaPlayer {
    @Override
    public void playVlc(String fileName) {
        // No hacer nada
    }

    @Override
    public void playMp4(String fileName) {
        System.out.println("Reproduciendo MP4 archivo: " + fileName);
    }
}
```
3. Crear el Adapter
```java
// Clase Adapter que implementa MediaPlayer y utiliza AdvancedMediaPlayer
class MediaAdapter implements MediaPlayer {
    AdvancedMediaPlayer advancedMediaPlayer;

    public MediaAdapter(String audioType) {
        if (audioType.equalsIgnoreCase("vlc")) {
            advancedMediaPlayer = new VlcPlayer();
        } else if (audioType.equalsIgnoreCase("mp4")) {
            advancedMediaPlayer = new Mp4Player();
        }
    }

    @Override
    public void play(String audioType, String fileName) {
        if (audioType.equalsIgnoreCase("vlc")) {
            advancedMediaPlayer.playVlc(fileName);
        } else if (audioType.equalsIgnoreCase("mp4")) {
            advancedMediaPlayer.playMp4(fileName);
        }
    }
}
```
4. Implementar la clase de reproductor de audio que utiliza el Adapter
```java
// Implementación de MediaPlayer
class AudioPlayer implements MediaPlayer {
    MediaAdapter mediaAdapter;

    @Override
    public void play(String audioType, String fileName) {
        // Reproducción de archivos de audio predeterminados
        if (audioType.equalsIgnoreCase("mp3")) {
            System.out.println("Reproduciendo MP3 archivo: " + fileName);
        }
        // Utilizar el adapter para otros tipos de audio
        else if (audioType.equalsIgnoreCase("vlc") || audioType.equalsIgnoreCase("mp4")) {
            mediaAdapter = new MediaAdapter(audioType);
            mediaAdapter.play(audioType, fileName);
        } else {
            System.out.println("Tipo de audio no soportado: " + audioType);
        }
    }
}
```
5. Uso del patrón Adapter
```java
public class AdapterPatternDemo {
    public static void main(String[] args) {
        AudioPlayer audioPlayer = new AudioPlayer();

        audioPlayer.play("mp3", "cancion.mp3");
        audioPlayer.play("mp4", "video.mp4");
        audioPlayer.play("vlc", "pelicula.vlc");
        audioPlayer.play("avi", "serie.avi");
    }
}
```
### Explicación del código:
1. **Interfaces**: **MediaPlayer** y **AdvancedMediaPlayer** definen las interfaces para los reproductores de medios.
2. **Clases Concretas**: **VlcPlayer** y **Mp4Player** implementan la interfaz **AdvancedMediaPlayer**.
3. **Adapter**: **MediaAdapter** implementa **MediaPlayer** y actúa como un puente para **AdvancedMediaPlayer**.
4. **Uso del Adapter**: **AudioPlayer** utiliza **MediaAdapter** para reproducir formatos avanzados.
5. **Demo**: En **AdapterPatternDemo**, se demuestra cómo **AudioPlayer** puede reproducir diferentes tipos de archivos de audio,
   incluso utilizando el Adapter para formatos no soportados directamente.
