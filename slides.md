# ジェネバ機構をTinkercadでプログラミングしてつくろう！


<a href="https://creativecommons.org/licenses/by-sa/4.0/deed.ja"><img src="/by-sa.webp" style="width: 10%"></a>
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.ja)にしたがって公開します。

<kbd>←</kbd> で戻る。<kbd>→</kbd> で進む。

---

# ジェネバ機構とは？

ジェネバ機構は、連続で回転する運動を、少しずつ断続的に回転する運動に変えることができる機構です。

<div class="flex justify-center">
　　<img src="/Geneva_mechanism_6spoke_animation.gif" style="width: 50%">
</div>

<small>画像: ジェネバ機構. (2023, August 28). In Wikipedia. https://ja.wikipedia.org/wiki/%E3%82%B8%E3%82%A7%E3%83%8D%E3%83%90%E6%A9%9F%E6%A7%8B</small>

---

# Tinkercadでプログラミングしてつくろう

ジェネバ機構の3Dモデルを、Tinkercadのコードブロックを使い、プログラミングしてつくってみましょう。

<div class="flex justify-center">
　　<img src="/geneva_drive_demo.gif" style="width: 80%">
</div>

---
layout: two-cols
---

# ジェネバ機構の各部品

<div class="flex justify-center">
　　<img src="/geneva_drive_overview.png">
</div>


::right::

<div style="margin-top:100px">

- 原動車(連続回転する部分)
- 従動車(断続的に回転する部分)
- 台

の3つのパーツを作っていきます。
</div>

---

# 初期設定

スロットが4つのジェネバ機構をつくっていきます。

各パーツの主要な部分の長さを、初期化の処理で以下のように設定します。

<div class="flex justify-center">
　　<img src="/initialization.png">
</div>

---

# 原動車と従動車の位置関係

原動車や従動車の位置関係を見ていきます。

スロットが4つの場合、原動車のピンが従動車と接したとき、原動車の中心・ピン・従動車の中心の3点を結んだ三角形は、直角以外の角度がそれぞれ45度(180 / 4 = 45 なので)の二等辺直角三角形になります。

<div class="flex justify-center">
　　<img src="/geneva_drive.png" style="width: 50%">
</div>

<small>次の画像を元にリミックス: ジェネバ機構. (2023, August 28). In Wikipedia. https://ja.wikipedia.org/wiki/%E3%82%B8%E3%82%A7%E3%83%8D%E3%83%90%E6%A9%9F%E6%A7%8B</small>
---

# 原動車下部の半径

原動車と従動車との中心間の距離が30mmのとき、ピンが位置する原動車下部の半径は30/√2です。(原動車下部半径 : 中心間の距離 の比率が 1:√2 なので)

<div class="flex justify-center">
　　<img src="/drive_wheel_bottom_radius.png" style="width: 50%">
</div>

<small>次の画像を元にリミックス: ジェネバ機構. (2023, August 28). In Wikipedia. https://ja.wikipedia.org/wiki/%E3%82%B8%E3%82%A7%E3%83%8D%E3%83%90%E6%A9%9F%E6%A7%8B</small>
---

# 従動車の半径

原動車と従動車との中心間の距離が30mmのとき、従動車の半径も30/√2です。(従動車の半径 : 中心間の距離 の比率が 1:√2 なので)


<div class="flex justify-center">
　　<img src="/driven_wheel_radius.png" style="width: 50%">
</div>

<small>次の画像を元にリミックス: ジェネバ機構. (2023, August 28). In Wikipedia. https://ja.wikipedia.org/wiki/%E3%82%B8%E3%82%A7%E3%83%8D%E3%83%90%E6%A9%9F%E6%A7%8B</small>
---

# 原動車上部の半径

原動車の中心と従動車の中心とを結んだ直線に、ピンから垂線を下ろし、ピンの半径を足した地点が原動車上部の半径にあたります。

90度、45度、45度の直角三角形の場合、この長さは一番長い辺の半分とピンの半径を足した値になり、15mm + ピンの半径 になります。

<div class="flex justify-center">
　　<img src="/drive_wheel_top_radius.png" style="width: 40%">
</div>

<small>次の画像を元にリミックス: ジェネバ機構. (2023, August 28). In Wikipedia. https://ja.wikipedia.org/wiki/%E3%82%B8%E3%82%A7%E3%83%8D%E3%83%90%E6%A9%9F%E6%A7%8B</small>
---

# 初期設定

以上の各パーツの位置関係をもとに、初期化の処理をもう一度確認しましょう。

Tinkercadの「+ 作成」ボタンをクリックし、コードブロックを選んで以下の初期化の処理をつくります。

<div class="flex justify-center">
　　<img src="/initialization.png">
</div>

---

# 原動車上部をつくる

次に原動車の上の部分をつくります。

「原動車上部の半径」を半径とする円形部分をつくり、「中心間の距離(30mm)」だけ離した「従動車の半径」 + 「マージン」の半径の円形部分で切り取ります。そのあと、高さ5mmまで持ち上げます。

<div class="flex justify-center">
　　<img src="/drive_wheel_top.gif">
</div>

---

# 原動車下部をつくる

次に原動車の下の部分をつくります。

「原動車下部の半径」を半径とする円形部分をつくり、「原動車下部の半径」離した場所に「ピンの半径」を半径とした円柱をつくります。それぞれ高さ0mm(底面)に持ち上げます。（何も指定しないと各オブジェクトは底面を中心として作成されるので）

<div class="flex justify-center">
　　<img src="/drive_wheel_bottom.gif" style="width: 80%">
</div>

---

# 原動車の中心に穴をあける

原動車の中心に「軸の半径」+「マージン」/2 を半径とする穴をあけます。

このあと従動車をつくるので、邪魔にならないように「従動車の半径」+「マージン」だけ横に移動してよけておきます。

<div class="flex justify-center">
　　<img src="/drive_wheel_center.gif">
</div>

---

# 従動車の円形部分のスロット(穴)をつくる

これから従動車をつくっていきます。

はじめに「中心間の距離」+「原動車上部の半径」+「マージン」の大きな円盤をつくり、邪魔にならないよう底面より下に沈めます。つぎに「原動車上部の半径」+「マージン」を半径とする円盤を4つ十字状にならべます。大きな円盤をあらかじめつくったのは、小さな円盤を（それ自体の中心ではなく）原点を中心として回転させたかったからです。

<div class="flex justify-center">
　　<img src="/driven_wheel_round_slots.gif" style="width: 80%">
</div>

---

# 従動車の直方体のスロット(穴)をつくる

次に直方体のスロット(穴)をつくります。

横幅が「原動車下部の半径」+「ピンの半径」+「マージン」、縦幅が「ピンの半径」x 2 + 「マージン」(ピンが入るように)の直方体を4つ、これらも十字状にならべます。最後にまとめてグループ化し、穴に変換します。

<div class="flex justify-center">
　　<img src="/driven_wheel_box_slots.gif">
</div>

---

# 従動車(本体)をつくる

次に従動車の本体をつくります。

「従動車の半径」を半径として円盤をつくり、円形と直方体を組み合わせてつくった穴で切り取ります。そのあと、高さ5mmまで持ち上げます。

<div class="flex justify-center">
　　<img src="/driven_wheel.gif" style="width: 90%">
</div>

---

# 従動車の下の部分をつくり、中心に穴をあける

直方体の穴の部分と重ならないぎりぎりのところまでを占める円柱を、従動車の下の部分につくります。

「中心間の距離」- (「原動車下部の半径」+「ピンの半径」+「マージン」)が半径の長さです。次に、従動車の中心に「軸の半径」+「マージン」/2 を半径とする穴をあけます。最後に、3Dプリンターで出力しやすいように大きな部分が底面にくるように反転しています。

<div class="flex justify-center">
　　<img src="/driven_wheel_center.gif">
</div>

---

# 台をつくる

原動車と従動車が乗るように横幅が「原動車下部の半径」+「中心間の距離」+「従動車」、縦が 「原動車下部の半径」x 2 の長さの台をつくります。「軸の半径」を半径とする円柱をつくり、原動車の中心と従動車の中心の部分に立てます。最後に原動車あるいは従動車と重ならないように縦方向にずらしています。

<div class="flex justify-center">
　　<img src="/stand.gif">
</div>

---

# まとめ

それぞれのパーツはテンプレートの機能を使い、各テンプレートに定義しています。

最後に全部のテンプレートを順番に呼び出しています。

<div class="flex justify-center">
　　<img src="/templates.png" style="width: 70%;">
</div>

---

# 3Dモデルでプリント

STLファイルとしてエクスポートすれば、3Dプリンターで出力することができます。

<iframe style="margin: 0 auto;" width="203" height="362" src="https://www.youtube.com/embed/Ud-0BkLBQJY" title="geneva drive(4 slots)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


---

# Tinkercad のリンク

紹介したTinkercadコードブロックのコードは以下のリンク先で公開しているので、ご自由にお使いください。

- [4スロットジェネバ機構](https://www.tinkercad.com/codeblocks/ciX5umKiYkE-4)

---

# 参考リンク

- https://ja.wikipedia.org/wiki/%E3%82%B8%E3%82%A7%E3%83%8D%E3%83%90%E6%A9%9F%E6%A7%8B
- [機械式時計のために開発された「ゼネバ機構」とは](https://monoist.itmedia.co.jp/mn/articles/2007/10/news013.html)
- [Inventor / ゼネバ機構｜オクターブ・ラボ](https://note.com/yo420186/n/n914aca93dc2b)
- [Make Geneva Wheels of Any Size in a Easier Way](https://www.instructables.com/Make-Geneva-Wheels-of-Any-Size-in-a-Easier-Way/)

---
layout: center
---

<a href="https://creativecommons.org/licenses/by-sa/4.0/deed.ja"><img src="/by-sa.webp" style="width: 10%"></a>
この文書は[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.ja)にしたがって公開します。

Markdown形式だけで書ける[Slidev](https://ja.sli.dev/)というツールを使って作っており、GitHub(https://github.com/champierre/geneva-drive)でソースを公開しています。

リミックス、間違いの指摘、改善提案など歓迎します。
