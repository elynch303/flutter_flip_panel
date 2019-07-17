# Flip Panel Web

[![pub package](https://img.shields.io/pub/v/flip_panel.svg)](https://pub.dartlang.org/packages/flip_panel) [![Build Status](https://travis-ci.org/elynch303/flutter_flip_panel.svg?branch=master)](https://travis-ci.org/elynch303/flutter_flip_panel)

A package for flip panel with built-in animation

Web Version based on [Flip Panel](https://github.com/hnvn/flutter_flip_panel)

<p>
	<img src="https://github.com/elynch303/flutter_flip_panel/blob/master/screenshots/flip_image.gif?raw=true" width="250" height="443"  />
	<img src="https://github.com/elynch303/flutter_flip_panel/blob/master/screenshots/flip_clock.gif?raw=true" width="250" height="443" />
</p>

## How to use

````dart
import 'package:flip_panel_web/flip_panel_web.dart';
````

Create a flip panel from iterable source:

````dart
final digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

FlipPanel.builder(
    itemBuilder: (context, index) => Container(
       color: Colors.black,
       padding: const EdgeInsets.symmetric(horizontal: 6.0),
       child: Text(
         '${digits[index]}',
         style: TextStyle(
             fontWeight: FontWeight.bold,
             fontSize: 50.0,
             color: Colors.white),
       ),
     ),
    itemsCount: digits.length,
    period: const Duration(milliseconds: 1000),
    loop: 1,
)
````

Create a flip panel from stream source:

````dart
FlipPanel<int>.stream(
      itemStream: Stream.periodic(Duration(milliseconds: 1000), (count) => count % 10),
      itemBuilder: (context, value) => Container(
        color: Colors.black,
        padding: const EdgeInsets.symmetric(horizontal: 6.0),
        child: Text(
          '$value',
          style: TextStyle(
            fontWeight: FontWeight.bold,
            fontSize: 50.0,
            color: Colors.white
          ),
        ),
      ),
      initValue: 0,
  );

````

<!-- NOTE: [flutter_web](https://github.com/flutter/flutter_web) packages are not published to pub.dartlang.org so the overrides are commented UNCOMMENT befor using   -->
