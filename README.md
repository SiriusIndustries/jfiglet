# jfiglet

Java implementation of FIGfonts to create ascii art banners. My goals were:

- distributed as a maven dependency
- should be small

I started out from Benoît Rigaut, Juillet work found at [www.rigaut.com](http://www.rigaut.com/benoit/CERN/FigletJava/)

## Figlet

[figlet](http://www.figlet.org/) is a command-line tool which helps you to create ascii banners like this:

```
     _  _____  ___   ____  _      _____  _____
    | ||  ___||_ _| / ___|| |    | ____||_   _|
 _  | || |_    | | | |  _ | |    |  _|    | |  
| |_| ||  _|   | | | |_| || |___ | |___   | |  
 \___/ |_|    |___| \____||_____||_____|  |_|  
```

Figlet has a *specification* which is included into the repo for easy access [here](https://github.com/lalyos/jfiglet/blob/master/figfont.txt)

## Usage
you can use it from command line or from java code

## Maven dependency

add the following maven dependency to your `pom.xml`

```
<dependency>
	<groupId>com.github.lalyos</groupId>
	<artifactId>jfiglet</artifactId>
	<version>0.0.2</version>
</dependency>
```

### Snapshot repo

Or if you want to use the latest development version, you can use the github based snapshot repo:

```
<repositories>
    <repository>
        <id>lalyos-snapshots</id>
        <url>https://github.com/lalyos/mvn-repo/raw/master/snapshots</url>
    </repository>
</repositories>

<dependency>
    <groupId>com.github.lalyos</groupId>
    <artifactId>jfiglet</artifactId>
    <version>0.0.3-SNAPSHOT</version>
</dependency>
```

Then use the `convertOneLine()` static method to do the magic

```
import com.github.lalyos.jfiglet.FigletFont;

public class App {
  public static void main(String[] args) {
    String asciiArt = FigletFont.convertOneLine("hello");
    System.out.println(asciiArt);
  }
}

```

## command line

You can use the jar from the central repo, or use the latest development version from sourcecode;

### from source

```
git clone git@github.com:lalyos/jfiglet.git
cd jfiglet
mvn exec:java -Dexec.arguments="jfiglet rulez"
```
### from maven central

```
curl -o jfiglet.jar http://central.maven.org/maven2/com/github/lalyos/jfiglet/0.0.2/jfiglet-0.0.2.jar
java -jar jfiglet.jar "text to convert"
```


## Related projects

First I wrapped http://artii.herokuapp.com/ which is based on the artii gem
I found 2 java implementations:
- http://www.jave.de/eclipse/figlet/index.html its not just FIGlet its  much more, includes swing editor and so ...
- http://www.rigaut.com/benoit/CERN/FigletJava/ it contains a single class implementation, so i choose this one.


## Todo

- *smush*-ing: *kerning* is already implemented  as default, smushing needs some coding.
- add more fonts: first i wanted to keep it small, but want to deliver a couple of fonts included in the jar, or maybe as a separate maven dependency
