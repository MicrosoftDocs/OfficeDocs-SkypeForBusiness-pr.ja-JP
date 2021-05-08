---
title: 管理センター称賛アプリをTeamsする
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jozhuan
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: 管理センターの 称賛 アプリの管理者設定Microsoft Teamsする
ms.openlocfilehash: becaccc9c8370d25e3d085e3c896d4f1a8a0ad95
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995185"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>管理センター称賛アプリをMicrosoft Teamsする

> [!NOTE]
> 管理者は、この機能にアクセスTeamsライセンスを持っている必要があります。 ライセンスなしでこの機能にアクセスTeams、エラー メッセージが表示されます。

この称賛アプリはMicrosoft Teams、ユーザーが自分の組織または教室のメンバーに感謝の気持ちを示すのに役立ちます。 選択できるバッジ セットと独自のバッジを作成するオプションにより、称賛 は、教師から Frontline Worker まで、Teams ユーザーが行う幅広い作業に取り組む作業を認識するのに役立ちます。 詳細については、「ユーザーにメールを[送信称賛」を参照してください](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)。

管理者は、管理センターから組織が使用できるバッジMicrosoft Teamsできます。 左側のナビゲーションで、[アプリの管理] **Teamsアプリ> に移動します**。 アプリの一覧で 、[次へ]**を称賛** し、[] を選択 **設定。**  ここから、既定の組み込みのバッジ セットを有効にし、カスタム バッジを作成することができます。

![アプリの [設定] タブ称賛スクリーンショット](media/manage-praise-app-settings.png)

> [!NOTE]
> この称賛アプリの機能は、米国政府のクラウドでは使用できません。

## <a name="use-built-in-badge-sets"></a>組み込みのバッジ セットを使用する

組み込みセットは、Microsoft が設計したアプリ用に設計されたバッジ称賛です。 これらのセットは管理者が編集できません。 既定のバッジ セットは既に有効であり、称賛できます。 既定のセットまたはバッジ セットの可用性を変更するには、対応するトグルを [オン] または [オフ] に切り替えます。 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>既定のバッジ

既定のバッジ セットは、ユーザーが仕事Teamsを超えて行く同僚を認識するのに役立ちます。

![既定のバッジ セットのプレビュー](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>教育用のソーシャルおよび感情的な学習バッジ

教師は、ソーシャルおよび感情学習 (SEL) の実績と行動について、これらの概念を示すバッジを使用して個々の学生を認識できます。

![教育用のソーシャルおよび感情的な学習バッジのプレビュー](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>独自のバッジを作成する

[カスタム **バッジの作成] を選択します**。 ここから、サイド パネルでカスタム バッジをデザインできます。 最大 25 のカスタム バッジを作成できます。 

![[カスタム バッジの作成] ウィンドウのスクリーンショット](media/manage-praise-app-create-custom-badge.png)

1. バッジ名を入力します。 これは、ユーザーが称賛を送信するときにバッジに表示される名前です。

2. バッジの色を設定します。 バッジのテキストと背景色を設定するには、16 進数 (16 進) 値として色を入力する必要があります。

   > [!TIP]
   > 16 進値を初めから使用する場合[](#hex-colors-intro)は、その使い方を簡単に説明します。

3. アップロード画像を作成します。 受け入れられるファイルの種類は.PNG。 イメージ ファイルは 40 KB 未満で、最大サイズは 216 X 216 ピクセルである必要があります。
![背景、テキスト、画像のフィールドにラベルが付いたバッジ](media/praise-app-badge-fields.png)

4. バッジ名をローカライズする: [ローカライズされたバッジ **名] で、[** 追加] を **選択します**。 ドロップダウン リストから目的のロケールを選択します。 次に、指定された言語でバッジ名を入力します。

5. 特定の地域からバッジを除外する: [これらの地域から **バッジ** を除外する] で、[追加] を **選択します**。 ドロップダウン リストから除外する地域を選択します。

6. **[適用]** を選択します。 これで、新しいバッジがカスタム バッジ テーブルに表示されます。

> [!NOTE]
> 手順 4 と 5 がスキップされた場合、バッジは、すべての地域の既定の言語になります。
>
> バッジの選択に変更を加え終わったら、[送信] を選択 **します**。 組織でこれらの変更を利用するには、最大で数時間かかる場合があります。

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>16 進値を使用して色を指定する

16 進数の色の値は、00 から FF のスケールで特定の色の赤 (RR)、緑 (GG)、青 (BB) の強度を表す 6 桁の 16 進数の文字列です。 3 色すべての値をまとめて入力すると、16 進数の値が表示#RRGGBB

たとえば、赤色の 16 進値は #FF0000 になります。赤は可能な限り高い値に設定され、FF、緑、青は、それぞれ可能な限り小さい値 00 に設定されます。

さまざまな色とその 16 進値を調Bing[を確認してください](https://www.bing.com/search?q=color+picker)。

使用を開始する色の例を次に示します。

|色  |16 進値|
|-------|---------|
|![16 進カラー #FF6666](media/hexColor1.png)|  #FF6666   |
|![16 進カラー #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![16 進カラー #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![16 進カラー #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![16 進カラー #800080](media/hexColor5.png)|  #800080   |
|![16 進カラー #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>カスタム バッジを作成するためのベスト プラクティス

**すべてのバッジを一度に送信します。** 新しいバッジが処理されるのに時間がかかるため、提出する前に、すべてのカスタム バッジをテーブルに追加する必要があります。

**色を選択する場合は、アクセシビリティに考慮してください。** 一部の色は、他の色よりも優れた色です。  テキストと背景色のコントラストを作成して、バッジ名を読みやすくします。 たとえば、濃い背景色を選んだ場合は、明るいテキストの色を選ぶとします。

**画像を選択する場合は、バッジのサイズを念頭に置きます。** 最適な品質を得る場合は、216 x 216 ピクセル (最大サイズ) のイメージ ファイルをアップロードすることをお勧めします。 これらの寸法に合わせて画像を拡大または歪ませないでください。

**バッジ画像が四角形ではない場合は、画像を透明にします。** イメージ ファイルをアップロードする前に、この操作を行う称賛。

![左: 透明でない画像を含むバッジ、右: 透明な画像を含むバッジ](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>バッジ セットアセット

組み込みのバッジ セットは変更できません。そのため、組み込みセットが有効になっていると、セット内のすべてのバッジが 称賛されます。 組み込みのセットから特定のバッジを追加し、他のバッジを削除する場合は、カスタム バッジとして使用するバッジを再作成します。 バッジ画像をダウンロードし、次の表の組み込みセットからバッジのテキストと背景色を見つけることができます。

### <a name="default-badges-assets"></a>既定のバッジ アセット

</br>

|バッジ名     |イメージ ファイル  |テキストの色 | 背景色 |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|すごい        |[Awesome PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|コーチ          |[コーチ PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|しだい        |[しだい PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|クリエイティブ       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|包括的      |[包括的な PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|リーダーシップ     |[リーダーシップ PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|オプティミム       |[オプティミム PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|問題の解決 |[問題解決の PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|チーム プレイヤー    |[チーム プレイヤー PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|ありがとう      |[PNG ありがとうございます](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>教育資産のソーシャルおよび感情的な学習バッジ

</br>

|バッジ名        |イメージ ファイル  |テキストの色 | 背景色 |
|------------------|------------|---------- |--------|
|コミュニケーション     |[通信 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|重大な思考 |[クリティカル な思考の PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|大自然         |[しなやか PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|共感           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|目標達成      |[ゴール パトゴール PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|動機        |[動機 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|永続化       |[永続化 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|尊重           |[PNG を尊重する](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|責任    |[Responsibility PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|自己認識    |[自己認識 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|自己管理   |[自己管理 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|思いやり    |[思いやりの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
