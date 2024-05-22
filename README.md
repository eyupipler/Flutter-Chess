[![Testler](https://github.com/lichess-org/flutter-chessground/workflows/Test/badge.svg)](https://github.com/lichess-org/flutter-chessground/actions?query=workflow%3A%22Test%22)
[![pub paketi](https://img.shields.io/pub/v/chessground.svg)](https://pub.dev/packages/chessground)
[![paket yayıncısı](https://img.shields.io/pub/publisher/chessground.svg)](https://pub.dev/packages/chessground/publisher)
[![Discord](https://img.shields.io/discord/280713822073913354?label=Discord&logo=discord&style=flat)](https://discord.com/channels/280713822073913354/807722604478988348)

Chessground, lichess.org için geliştirilmiş bir satranç tahtası paketidir. Bu işlem yapmaz
satranç mantığı, böylece farklı satranç varyantları ile kullanabilirsiniz.

## Özellikler

- parça animasyonları: hareket etme ve kaybolma
- Tahtada öne çıkanlar: son hamle, taş hedefleri
- dokunarak veya sürükleyip bırakarak parçayı hareket ettirme
- premoves
- bırakılan kare hedefini belirtmek için sürüklenen parçanın altında bir gölge görüntüler
- pano temaları
- lichess'ten parça setleri
- promosyon seçi̇ci̇si̇
- tahtaya oklar çizin
- ek açıklamaları taşı
- android 10+ navigasyon hareketlerini pano etrafında hariç tutun (sürükleyici moda ihtiyaç duyar)

## Başlarken

Bu paket, etkileşimli veya etkileşimsiz olabilen bir `Board` widget`ı ihraç eder. Bu
tamamen bir `BoardSettings` nesnesi ile yapılandırılabilir.

## Kullanım

Bu, başlangıç konumundan itibaren etkileşimsiz bir tahta görüntüleyecektir.
varsayılan tema:

```dart
import 'package:flutter/material.dart';
import 'package:chessground/chessground.dart';

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String fen = 'rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR';

  @override
  Widget build(BuildContext context) {
    final double screenWidth = MediaQuery.of(context).size.width;

    return Scaffold(
      appBar: AppBar(
        title: const Text('Chessground demo'),
      ),
      body: Center(
        child: Board(
          size: screenWidth,
          data: BoardData(
            interactableSide: InteractableSide.none,
            orientation: Side.white,
            fen: fen,
          ),
        ),
      ),
    );
  }
}
```

Rastgele bir bota karşı etkileşimli bir sürüm için örnek uygulamaya bakın.

# ------------------------------------------------------------------------------

[![Tests](https://github.com/lichess-org/flutter-chessground/workflows/Test/badge.svg)](https://github.com/lichess-org/flutter-chessground/actions?query=workflow%3A%22Test%22)
[![pub package](https://img.shields.io/pub/v/chessground.svg)](https://pub.dev/packages/chessground)

Chessground is a chessboard package developed for lichess.org. It doesn't handle
chess logic so you can use it with different chess variants.

## Features

- pieces animations: moving and fading away
- board highlights: last move, piece destinations
- move piece by tap or drag and drop
- premoves
- displays a shadow under dragged piece to indicate the drop square target
- board themes
- piece sets from lichess
- promotion selector
- draw arrows on board
- move annotations
- exclude android 10+ navigation gestures around board (needs immersive mode)

## Getting started

This package exports a `Board` widget which can be interactable or not. It is
entirely configurable with a `BoardSettings` object.

## Usage

This will display a non-interactable board from the starting position, using the
default theme:

```dart
import 'package:flutter/material.dart';
import 'package:chessground/chessground.dart';

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String fen = 'rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR';

  @override
  Widget build(BuildContext context) {
    final double screenWidth = MediaQuery.of(context).size.width;

    return Scaffold(
      appBar: AppBar(
        title: const Text('Chessground demo'),
      ),
      body: Center(
        child: Board(
          size: screenWidth,
          data: BoardData(
            interactableSide: InteractableSide.none,
            orientation: Side.white,
            fen: fen,
          ),
        ),
      ),
    );
  }
}
```

See the example app for an interactable version against a random bot.
