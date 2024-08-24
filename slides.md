# Let's Program and Create a Geneva Drive in Tinkercad!


Published under <a href="https://creativecommons.org/licenses/by-sa/4.0/deed.en"><img src="/by-sa.webp" style="width: 10%"></a> [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

<kbd>←</kbd> Go back. <kbd>→</kbd> Move forward.

---

# What is a Geneva Drive?

The Geneva drive is a mechanism that can convert continuous rotational motion into intermittent rotational motion.

<div class="flex justify-center">
　　<img src="/Geneva_mechanism_6spoke_animation.gif" style="width: 50%">
</div>

<small>Geneva drive. (2024, July 31). In Wikipedia. https://en.wikipedia.org/wiki/Geneva_drive</small>

---

# Let's Program in Tinkercad

Let’s create a 3D model of a Geneva drive using Codeblocks in Tinkercad.

<div class="flex justify-center">
　　<img src="/geneva_drive_demo.gif" style="width: 80%">
</div>

---
layout: two-cols
---

# Parts of the Geneva Drive

<div class="flex justify-center">
　　<img src="/geneva_drive_overview.png">
</div>


::right::

<div style="margin-top:100px">

- Drive Wheel (continuously rotating part)
- Driven Wheel (intermittently rotating part)
- Stand

Let's create these three parts.
</div>

---

# Initial Setup

We'll start by creating a Geneva drive with four slots.

Let’s set the main dimensions of each part in the initialization process as follows:

<div class="flex justify-center">
　　<img src="/initialization.png" style="width: 80%">
</div>

---

# Positioning the Drive and Driven Wheels

Let’s look at the relative positions of the drive and driven wheels.

With a four-slot design, when the drive wheel’s pin engages the driven wheel, the triangle formed by the centers of the drive wheel, the pin, and the driven wheel's center is an isosceles right triangle with the other angles being 45 degrees each (180 / 4 = 45).

<div class="flex justify-center">
　　<img src="/geneva_drive.png" style="width: 50%">
</div>

<small>Remixed based on the next image: Geneva drive. (2024, July 31). In Wikipedia. https://en.wikipedia.org/wiki/Geneva_drive</small>
---

# Radius of the Bottom Part of the Drive Wheel

When the distance between the centers of the drive and driven wheels is 30mm, the radius at the bottom part of the drive wheel where the pin is located is 30/√2 (since the ratio of the bottom radius to the center distance is 1 : √2) mm.

<div class="flex justify-center">
　　<img src="/drive_wheel_bottom_radius.png" style="width: 50%">
</div>

<small>Remixed based on the next image: Geneva drive. (2024, July 31). In Wikipedia. https://en.wikipedia.org/wiki/Geneva_drive</small>
---

# Radius of the Driven Wheel

When the distance between the centers of the drive and driven wheels is 30mm, the radius of the driven wheel is also 30/√2 (since the ratio of the driven wheel's radius to the center distance is 1 : √2) mm.

<div class="flex justify-center">
　　<img src="/driven_wheel_radius.png" style="width: 50%">
</div>

<small>Remixed based on the next image: Geneva drive. (2024, July 31). In Wikipedia. https://en.wikipedia.org/wiki/Geneva_drive</small>
---

# Radius of the Top Part of the Drive Wheel

The radius at the top part of the drive wheel is determined by drawing a perpendicular from the pin to the line connecting the centers of the drive and driven wheels, adding the radius of the pin.

In the case of a right triangle with angles of 90, 45, and 45 degrees, this length is half of the longest side plus the radius of the pin, resulting in 15mm + <span class="variable">pin radius</span>.

<div class="flex justify-center">
　　<img src="/drive_wheel_top_radius.png" style="width: 30%">
</div>

<small>Remixed based on the next image: Geneva drive. (2024, July 31). In Wikipedia. https://en.wikipedia.org/wiki/Geneva_drive</small>
---

# Review the Initial Setup

Let's review the initial setup process once more based on the relative positions of each part.

Click the **+ Create** button in Tinkercad, select **Codeblocks** and create the following initialization process.

<div class="flex justify-center">
　　<img src="/initialization.png" style="width: 80%">
</div>

---

# Creating the Top Part of the Drive Wheel

Next, let's create the top part of the drive wheel.

Create a circular section with a radius of <span class="variable">drive wheel top radius</span> and subtract a circular section with a radius of <span class="variable">driven wheel radius</span> + <span class="variable">margin</span> separated by the distance of <span class="variable">centers distance</span>(30mm), then lift it up to a height of 5mm.

<div class="flex justify-center">
　　<img src="/drive_wheel_top.gif" style="width: 70%">
</div>

---

# Creating the Bottom Part of the Drive Wheel

Next, let's create the bottom part of the drive wheel.

Create a circular section with a radius of <span class="variable">drive wheel bottom radius</span>, and at a distance equal to the <span class="variable">drive wheel bottom radius</span>, create a cylinder with a radius of <span class="variable">pin radius</span>. Both are lifted to a height of 0mm (base).

<div class="flex justify-center">
　　<img src="/drive_wheel_bottom.gif" style="width: 70%">
</div>

---

# Creating a Hole at the Center of the Drive Wheel

Create a hole in the center of the drive wheel with a radius of <span class="variable">center pin radius</span> + (<span class="variable">margin</span> / 2).

Then, to avoid interference, move the driven wheel sideways by the <span class="variable">driven wheel radius</span> + <span class="variable">margin</span>.

<div class="flex justify-center">
　　<img src="/drive_wheel_center.gif" style="width: 70%">
</div>

---

# Creating the Circular Slots (Holes) of the Driven Wheel

Now, let's create the driven wheel.

First, create a large disc with a radius of <span class="variable">centers distance</span> + <span class="variable">drive wheel top radius</span> + <span class="variable">margin</span>, submerged below the base so that it does does not interfere with the creation of other parts. Next, arrange four small discs in a cross shape with a radius of <span class="variable">drive wheel top radius</span> + <span class="variable">margin</span>. The large disc was created first to allow the small discs to rotate around the origin, not their centers.

<div class="flex justify-center">
　　<img src="/driven_wheel_round_slots.gif" style="width: 50%">
</div>

---

# Creating the Rectangular Slots (Holes) of the Driven Wheel

Next, create rectangular slots (holes).

Arrange 4 rectangles with a width of <span class="variable">drive wheel bottom radius</span> + <span class="variable">pin radius</span> + <span class="variable">margin</span> and a height of <span class="variable">pin radius</span> x 2 + <span class="variable">margin</span>(to fit the pin) in a cross shape. Finally, group them together and convert to a Hole.

<div class="flex justify-center">
　　<img src="/driven_wheel_box_slots.gif" style="width: 65%">
</div>

---

# Creating the Body of the Driven Wheel

Next, let's create the body of the driven wheel.

Create a disc with a radius of <span class="variable">driven wheel radius</span>, and cut out using the combination of circular and rectangular slots created earlier. Then, lift it up to a height of 5mm.

<div class="flex justify-center">
　　<img src="/driven_wheel.gif" style="width: 70%">
</div>

---

# Creating the Bottom Part of the Driven Wheel and Making a Hole in the Center

Create a cylinder occupying the space up to just before overlapping with the rectangular slots at the bottom of the driven wheel.

The radius of this cylinder is <span class="variable">centers distance</span> - (<span class="variable">drive wheel bottom radius</span> + <span class="variable">pin radius</span> + <span class="variable">margin</span>). Next, make a hole in the center of the driven wheel with a radius of <span class="variable">center pin radius</span> + (<span class="variable">margin</span> / 2). Finally, invert it for easier 3D printing so that the larger part faces the base.

<div class="flex justify-center">
　　<img src="/driven_wheel_center.gif" style="width: 55%">
</div>

---

# Creating the Stand

Create a Stand with a width of <span class="variable">drive wheel bottom radius</span> + <span class="variable">centers distance</span> + <span class="variable">driven wheel radius</span> and a length of <span class="variable">drive wheel bottom radius</span> x 2. Create a cylinders with a radius of <span class="variable">center pin radius</span> and position them at the centers of the drive and driven wheels. Finally, shift it vertically to avoid overlapping with the drive or driven wheels.

<div class="flex justify-center">
　　<img src="/stand.gif" style="width: 70%">
</div>

---

# Summary

Each part is created using the Template feature, with each template defined.

Finally, all templates are called in sequence.

<div class="flex justify-center">
　　<img src="/templates.png" style="width: 40%;">
</div>

---

# 3D Printing the Model

If you export as an STL file, you can print it with a 3D printer.

<iframe style="margin: 0 auto;" width="203" height="362" src="https://www.youtube.com/embed/Ud-0BkLBQJY" title="geneva drive(4 slots)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


---

# Tinkercad Link

The code for the Tinkercad codeblock introduced here is available at the following link for you to use freely:

- [n slots Geneva drive(Codeblocks)](https://www.tinkercad.com/codeblocks/bJDl1VqaENx-n-slots-geneva-drivecodeblocks)

---

# Reference Links

- https://en.wikipedia.org/wiki/Geneva_drive
- [Make Geneva Wheels of Any Size in a Easier Way](https://www.instructables.com/Make-Geneva-Wheels-of-Any-Size-in-a-Easier-Way/)
- [機械式時計のために開発された「ゼネバ機構」とは (Japanese)](https://monoist.itmedia.co.jp/mn/articles/2007/10/news013.html)
- [Inventor / ゼネバ機構｜オクターブ・ラボ (Japanese)](https://note.com/yo420186/n/n914aca93dc2b)

---
layout: center
---

<a href="https://creativecommons.org/licenses/by-sa/4.0/deed.en"><img src="/by-sa.webp" style="width: 10%"></a>

This document is published under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

This slide is created using [Slidev](https://sli.dev/), and the source code is available on GitHub(https://github.com/champierre/geneva-drive-en).

Remixes, corrections, and suggestions for improvement are welcome.
