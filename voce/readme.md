# Voce Test and Proof of Concept

Keywords : Java Speech recognition api java voce speech FreeTTS CMU Sphinx Speech Recognizer Text To Speech voce.sourceforge.net speech recognition using Java and Sphinx Pure Java speech recognition library java SpeechRecognition

# Inspiration

I do this because I love artificial intelligence and I dream about the day when a true artificial intelligence can coexist with humans.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

- Java 7 or 8
- [Download Maven](http://maven.apache.org/download.cgi)
- [Install Maven](http://maven.apache.org/install.html)

In order to test this source code, the following maven libraries are required :

- clone and follow the **prerequisites and install** steps of this repository [https://github.com/jrichardsz/voce](https://github.com/jrichardsz/voce).

- install the acoustic model library:

```
mvn install:install-file -Dfile=offline-jars/WSJ_8gau_13dCep_16k_40mel_130Hz_6800Hz-1.0.jar -DgroupId=edu.cmu.sphinx.model.acoustic.WSJ_8gau_13dCep_16k_40mel_130Hz_6800Hz -DartifactId=WSJ_8gau_13dCep_16k_40mel_130Hz_6800Hz -Dversion=1.0 -Dpackaging=jar

```

...

## Running the tests

### Without Java IDE

If you dont like to use an IDE to run a simple java code, try this:

```
mvn clean package exec:java -Dexec.mainClass="org.jrichardsz.poc.voce.RecognitionTest" -Dexec.args="config-files"
```

- If no errors, wait to the following text appear and start to say any number from 0 to 9

```

[INFO]
[INFO] ----------------------------------------
[INFO] Building poc-voce-recognition 1.0.0
[INFO] ----------------------------------------
[INFO]
[INFO] --- maven-clean-plugin:2.5:clean (defaul
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources
[WARNING] Using platform encoding (Cp1252 actua
[INFO] Copying 2 resources

.....

voicePath:/some_folder/config-files\voice
grammarPath:/some_folder/config-files\grammar
grammarName:digits

[Voce debug] Beginning initialization
[Voce] Initializing recognizer. This may take some time...
[Voce debug] Starting microphone...
[Voce debug] Microphone on
[Voce] Initialization complete
[Voce debug] Recognition thread starting
This is a speech recognition test. Speak digits from 0-9 into the microphone. Speak 'quit' to quit.
```

- If no errors, this will be the log after you say any number from 0 to 9

```
You said: six
[Voce debug] Finished recognizing
You said: seven
[Voce debug] Finished recognizing
You said: one
[Voce debug] Finished recognizing
You said: two oh
[Voce debug] Finished recognizing
You said: three
```

...

# Custom grammar

In the previous test, we are used the default grammar and voce configurations. For real usage, move configuration files to any location in yout operative system. Example :

  [config-files](./config-files)

  **Note:** In windows s.o

  - Your config file must be in the same hard drive of cloned repository
  - If your config files are in

```
  D:\some_folder\config-files
```

  The correct value will be:

```
  \some_folder\config-files
```

- finally, execute this

```
mvn clean package exec:java -Dexec.mainClass="org.jrichardsz.poc.voce.RecognitionTest" -Dexec.args="/some_folder/config-files"
```

...

## Built With

* [Maven](https://www.apache.org/) - Apache Maven is a software project management and comprehension tool
* [Java](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html) - Java SE Development Kit 7 Downloads

## Contributing

....

## Coming Soon
Use the latest version of:

[http://cmusphinx.sourceforge.net/wiki/tutorial](http://cmusphinx.sourceforge.net/wiki/tutorial)

## Useful links

http://homepages.abdn.ac.uk/k.vdeemter/pages/teaching/NLP/practicals/JSGFGrammar.html

https://puneetk.com/basics-of-java-speech-grammar-format-jsgf

http://www.instructables.com/id/Animatronic-Talking-Tree-Part-2-Speech-Recogni/step4/Grammar-Files/

https://www.w3.org/TR/jsgf/

...

## Authors

* **Richard Osmar Leon Ingaruca** - *JRichardsz* - [contact me](http://jrichardsz.github.io)

## License

Voce is licensed under the BSD or LGPL Open Source licenses.  Also, be sure to read the licenses for [FreeTTS](http://freetts.sourceforge.net/docs/index.php) and [CMU Sphinx4](http://cmusphinx.sourceforge.net/wiki/tutorialsphinx4).
