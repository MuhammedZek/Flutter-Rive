<h1>Flutter Animation Project using Rive</h1>

<h2>Dark Loading Animation</h2>
<p align="center">
  <img src="https://github.com/tomkmangattu/flutter-rive-animation/blob/main/screenshots/screenshot1.jpg" width="250" title="Dark loading animation">
  <img src="https://github.com/tomkmangattu/flutter-rive-animation/blob/main/screenshots/screenshot2.jpg" width="250" title="Dark loading animation">
</p>

<h2>Light Loading Animation</h2>
<p align="center">
  <img src="https://github.com/tomkmangattu/flutter-rive-animation/blob/main/screenshots/screenshot3.jpg" width="250" title="Light loading animation">
  <img src="https://github.com/tomkmangattu/flutter-rive-animation/blob/main/screenshots/screenshot4.jpg" width="250" title="Light loading animation">
</p>

<h2>Animation code</h2>
  <h3>Initialise variables</h3>
  Artboard _artboard;
  RiveAnimationController _animationController;
  
  <h3>Add to InitState</h3>
  final bytes = await rootBundle.load(riveFile);
  RiveFile rFile = RiveFile.import(bytes);
  setState(() => _artboard = rFile.mainArtboard
      ..addController(_animationController = SimpleAnimation('dark')));
  
  <h3>change to tick</h3>
  _artboard.artboard.removeController(_animationController);
  _artboard.addController(SimpleAnimation('light_tick'));
  
  <h3>Add to dispose function</h3>
  _animationController.dispose();
  
  <h3>Finaly call the artboard</h3>
  _artboard != null
            ? Rive(
                artboard: _artboard,
              )
            : Container(),
            
            
            
Use homePage2 to avoid boiler plate codes. It uses RiveAnimation.asset() which came with new version of rive
