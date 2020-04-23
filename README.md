# animated-bottom-navigation-bar
AnimatedBottomNavigationBar is a customizable widget inspired by [dribble shot](https://dribbble.com/shots/7134849-Simple-Tab-Bar-Animation).

Made in [LANARS](https://dribbble.com/shots/7134849-Simple-Tab-Bar-Animation).

[![pub package](https://img.shields.io/pub/v/animated-bottom-navigation-bar.svg)](https://pub.dev/packages/animated_bottom_navigation_bar)
<a href="https://github.com/Solido/awesome-flutter">
   <img alt="Awesome Flutter" src="https://img.shields.io/badge/Awesome-Flutter-blue.svg?longCache=true&style=flat-square" />
</a>

<img src="/../master/doc/assets/animated-bottom-navigation-bar.gif" width="300">

# Getting Started

To get started, place your `AnimatedBottomNavigationBar` in the bottomNavigationBar slot of a `Scaffold`.
The `AnimatedBottomNavigationBar` respects `FloatingActionButton` location.
For example:

```dart
Scaffold(
   body: Container(), //destination screen
   floatingActionButton: FloatingActionButton(
      //params
   ),
   floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      gapLocation: GapLocation.center,
      notchSmoothness: NotchSmoothness.verySmoothEdge,
      leftCornerRadius: 32,
      rightCornerRadius: 32,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```

<img src="/../master/doc/assets/example-cornered-notched-bar.jpeg" width="300">

# Customization

AnimatedBottomNavigationBar is customizable and works with 2, 3, 4, or 5 navigation elements.
```dart
Scaffold(
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-plain-bar.jpeg" width="300">

```dart
Scaffold(
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      leftCornerRadius: 32,
      rightCornerRadius: 32,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-cornered-bar.jpeg" width="300">

```dart
Scaffold(
   floatingActionButton: FloatingActionButton(
      //params
   ),
   floatingActionButtonLocation: FloatingActionButtonLocation.endDocked,
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      gapLocation: GapLocation.end,
      notchSmoothness: NotchSmoothness.defaultEdge,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-notched-end.jpeg" width="300">

```dart
Scaffold(
   floatingActionButton: FloatingActionButton(
      //params
   ),
   floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      gapLocation: GapLocation.center,
      notchSmoothness: NotchSmoothness.defaultEdge,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-default-notch-center.jpeg" width="300">

```dart
Scaffold(
   floatingActionButton: FloatingActionButton(
      //params
   ),
   floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      gapLocation: GapLocation.center,
      notchSmoothness: NotchSmoothness.softEdge,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-soft-notch-center.jpeg" width="300">

```dart
Scaffold(
   floatingActionButton: FloatingActionButton(
      //params
   ),
   floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      gapLocation: GapLocation.center,
      notchSmoothness: NotchSmoothness.smoothEdge,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-smooth-notch-center.jpeg" width="300">

```dart
Scaffold(
   floatingActionButton: FloatingActionButton(
      //params
   ),
   floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
   bottomNavigationBar: AnimatedBottomNavigationBar(
      icons: iconList,
      activeIndex: _bottomNavIndex,
      gapLocation: GapLocation.center,
      notchSmoothness: NotchSmoothness.verySmoothEdge,
      onTap: (index) => setState(() => _bottomNavIndex = index),
      //other params
   ),
);
```
<img src="/../master/doc/assets/example-very-smooth-notch-center.jpeg" width="300">

# Driving Navigation Bar Changes

You have to change the active navigation bar tab programmatically by passing a new activeIndex to the AnimatedBottomNavigationBar widget.

```dart
class _MyAppState extends State<MyApp> {
  int activeIndex;

  /// Handler for when you want to programmatically change
  /// the active index. Calling `setState()` here causes
  /// Flutter to re-render the tree, which `AnimatedBottomNavigationBar`
  /// responds to by running its normal animation.
  void _onTap(int index) {
    setState((){
      activeIndex = index;
    });
  }

  Widget build(BuildContext context) {
    return AnimatedBottomNavigationBar(
      activeIndex: activeIndex,
      onTap: _onTap,
      //other params
    );
  }
}
```