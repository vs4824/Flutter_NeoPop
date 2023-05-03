# Flutter NeoPop

NeoPOP is CRED's inbuilt library for using NeoPOP components in your app.

## What really is NeoPOP?

NeoPOP was created with one simple goal; to create the next generation of a beautiful, affirmative design system. NeoPOP stays true to everything that design at CRED stands for.

NeoPOP is built for Android, iOS, Flutter and Web

## Installation

Add neopop as a dependency in your pubspec.yaml file.

   ```
   dependencies:
    neopop: ^1.0.2
   ```

## NeoPopButton

NeoPopButton render 5 surfaces, top, left, right, bottom and center. NeoPopButton widget gives you mutliple configs that you can use for your widget.

### Elevated

   ```
   NeoPopButton(
    color: Colors.white,
    onTapUp: () => HapticFeedback.vibrate(),
    onTapDown: () => HapticFeedback.vibrate(),
    child: Padding(
        padding: EdgeInsets.symmetric(horizontal: 20, vertical: 15),
        child: Row(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
                Text("Pay now"),
            ],
        ),
    ),
),
```

### Flat

By specifying the buttonPosition as Position.center, NeoPOP will compute right and bottom surface's color according to color. Top and left surface's color is computed w.r.t parentColor and grandparentColor

   ```
   NeoPopButton(
    color: Colors.white,
    onTapUp: () => HapticFeedback.vibrate(),
    onTapDown: () => HapticFeedback.vibrate(),
    parentColor: Colors.transparent,
    buttonPosition: Position.center,
    child: Padding(
        padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 15),
        child: Row(
            mainAxisAlignment: MainAxisAlignment.center,
            children: const [
                Text("Pay Now"),
            ],
        ),
    ),
),
   ```

### Shimmer

   ```
   const NeoPopShimmer(
    shimmerColor: Colors.yellow,
    child: Padding(
        padding: const EdgeInsets.symmetric(horizontal: 100, vertical: 15),
        child: Text("Hello"),
    ),
),
```

### Flat Strokes

To add border on a flat button, add border

   ```
   NeoPopButton(
    color: const Color.fromRGBO(0, 0, 0, 1),
    buttonPosition: Position.center,
    onTapUp: () {},
    border: const Border.fromBorderSide(
        BorderSide(color: kBorderColorWhite, width: kButtonBorderWidth),
    ),
    child: Padding(
        padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 15),
        child: Row(
            mainAxisAlignment: MainAxisAlignment.center,
            children: const [
                Text("Pay Now", style: TextStyle(color: Colors.white)),
            ],
        ),
    ),
),
   ```

### Elevated Strokes

   ```
   NeoPopButton(
    color: kSecondaryButtonLightColor,
    bottomShadowColor: ColorUtils.getVerticalShadow(kBorderColorGreen).toColor(),
    rightShadowColor: ColorUtils.getHorizontalShadow(kBorderColorGreen).toColor(),
    animationDuration: kButtonAnimationDuration,
    depth: kButtonDepth,
    onTapUp: () {},
    border: Border.all(
        color: kBorderColorGreen,
        width: kButtonBorderWidth,
    ),
    child: Padding(
        padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 15),
        child: Row(
            mainAxisAlignment: MainAxisAlignment.center,
            children: const [
                Text("Scan & Pay", style: TextStyle(color: Colors.white)),
            ],
        ),
    ),
),
```

### Adjacent Buttons

#### Vertically Aligned Buttons 

   ```
   Column(
    mainAxisSize: MainAxisSize.min,
    children: [
        NeoPopButton(
        color: kSecondaryButtonLightColor,
        bottomShadowColor: kShadowColorDarkGreen,
        rightShadowColor: kShadowColorGreen,
        buttonPosition: Position.fullBottom,
        onTapUp: () {},
        border: Border.all(
            color: kBorderColorGreen, width: kButtonBorderWidth,
        ),
        child:  const Padding(
                    padding: EdgeInsets.symmetric(horizontal: 8.0, vertical: 15.0),
                    child: Text(
                    "Button",
                    style: TextStyle(color: Colors.white),
                ),
            ),
        ),
        NeoPopButton(
            color: kPrimaryButtonColor,
            buttonPosition: Position.fullBottom,
            onTapUp: () {},
            child:  const Padding(
                padding: EdgeInsets.symmetric(horizontal: 8.0, vertical: 15.0),
                child: Text("Button"),
            ),
        ),
    ],
),
```

#### Horizontally Aligned Buttons

   ```
   Row(
    mainAxisSize: MainAxisSize.min,
    children: [
        Expanded(
        child: NeoPopButton(
            color: kPrimaryButtonColor,
            buttonPosition: Position.fullBottom,
            depth: kButtonDepth,
            onTapUp: () {},
            child: const Center(
            child:  Padding(
                    padding: EdgeInsets.symmetric(
                        horizontal: 8.0, vertical: 15.0),
                    child: Text("Button"),
                    ),
                ),
            ),
        ),
        Expanded(
            child: NeoPopButton(
                color: kSecondaryButtonLightColor,
                bottomShadowColor: kShadowColorDarkGreen,
                rightShadowColor: kShadowColorGreen,
                buttonPosition: Position.fullBottom,
                depth: kButtonDepth,
                onTapUp: () {},
                border: Border.all(
                    color: kBorderColorGreen, width: kButtonBorderWidth,
                ),
                child: const Center(
                child: Padding(
                    padding: EdgeInsets.symmetric( horizontal: 8.0, vertical: 15.0),
                    child: Text(
                            "Button",
                            style: TextStyle(color: Colors.white),
                        ),
                    ),
                ),
            ),
        ),
    ],
),
```
