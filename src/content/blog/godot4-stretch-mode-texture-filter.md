---
title: "Godot 4: Stretch Modes and Crisp Pixel Art Settings Explained"
description: "A quick guide on understanding Canvas Items vs. Viewport stretch modes and how to set up Nearest texture filtering for pixel art games in Godot 4."
pubDate: "Mar 01 2026"
heroImage: "/blog-placeholder-about.jpg"
---

# Understanding Stretch Modes and Texture Filtering in Godot 4

When setting up a new project in Godot 4, handling window resizing and graphics rendering can be a bit confusing. Here is a quick breakdown of how stretch modes and texture filters work, especially if you are aiming for a pixel art aesthetic.

## Stretch Mode: Canvas Items vs. Viewport

What exactly does it mean to stretch the window using the **Canvas Items** mode? 

When the game window shrinks or expands, the engine needs to adjust the coordinate system and aspect ratio. 
* **Canvas Items:** This mode scales the 2D coordinates but renders everything at the *actual* physical resolution of your current window. It keeps the UI and assets looking crisp at any screen size. 
* **Viewport:** This mode renders the entire game at your base resolution first, and then scales up that resulting image (like zooming in on a picture). 
* **Disabled:** The window size remains strictly locked to your original settings with no scaling applied.

## Texture Filter: Linear vs. Nearest

Texture filtering determines how the engine processes and displays image pixels. Modern rendering techniques favor smooth, anti-aliased lines. 

Because of this, Godot 4 uses a slight blur effect by default, which is the **Linear** filter. However, if you are making a pixel art game, this makes your sprites look blurry and washed out. 

* **Nearest:** This filter turns off the smoothing completely, rendering each individual pixel sharply and perfectly. 

Since I am developing a pixel art game, setting the Texture Filter to **Nearest** is a must. Of course, if I ever decide to switch from a pixel aesthetic to 3D models or vector-line graphics in the future, I will need to change this back to Linear.

---

## 🇰🇷 한국어 버전 (Korean Version)

# Godot 4 화면 늘리기 모드와 픽셀 아트 텍스처 필터 설정

## 늘리기 모드: Canvas Items와 Viewport

Q: Canvas Items 모드로 늘린다는 것은 무슨 말인가?

창이 줄어들거나 늘어날 때 모드가 변한다. 좌표계와 비율이 변하는 모드이다.
* **Canvas Items:** 좌표만 스케일링하고 현재 창의 실제 해상도로 렌더링을 진행한다는 말이다.
* **Viewport:** 기본 해상도를 먼저 그린 후, 그 이미지를 전체적으로 확대하는 느낌이다.
* **Disabled:** 창 크기가 기존에 설정한 대로만 유지되며 늘어나지 않는다.

## Texture Filter: Linear와 Nearest

Texture Filter는 이미지의 처리 방식이다. 최근 기술은 선을 부드럽게 보여주는 것이 대세여서 기본적으로 Godot 4에서는 Blur(블러) 효과를 주는 듯한 처리를 하고 있다. 그것이 **Linear**로 설정되어 있다.

* **Nearest:** 블러 처리 없이 하나하나의 픽셀을 또렷하게 보여주는 방식이다. 

나는 픽셀 게임을 개발하기 때문에 Filter를 **Nearest**로 설정했다. 혹시라도 나중에 픽셀 감성을 벗어난 3D나 벡터 라인의 이미지 게임을 만든다면 이 설정을 다시 바꾸어야 한다.