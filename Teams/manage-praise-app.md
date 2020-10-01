---
title: Teams 管理センターで称賛アプリを管理する
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Microsoft Teams 管理センターの称賛アプリでの管理設定について
ms.openlocfilehash: 9d293ebc0a9a8776f21bc0e4d1301380a50186a6
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328206"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで称賛アプリを管理する

Microsoft Teams の称賛アプリを使用すると、ユーザーは組織または教室のメンバーに対する感謝を示すことができます。 選択して、独自のバッジを作成するためのオプションを選ぶと、称賛は、チームユーザーが作成するさまざまな作業について、教育者から最初のラインワーカーまでの労力を認識できるように設計されています。

管理者は、Teams 管理センターで、組織が利用できるバッジを制御できます。 左側のナビゲーションで、[ **Teams アプリ] > [アプリの管理**] を選びます。 [テナントアプリカタログ](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)で称賛を開き、[**設定**] に移動します。

> [!Note]
> 米国政府機関の称賛アプリ機能は使用できません。

## <a name="use-built-in-badge-sets"></a>組み込みのバッジセットを使用する

組み込みセットは、称賛アプリ用に Microsoft によって設計されたバッジのコレクションです。 これらのセットは管理者が編集できません。 既定のバッジセットは既に有効になっており、称賛アプリで利用できます。 既定のセットまたはバッジセットの使用可能状態を変更するには、対応するトグルを [オン] または [オフ] に切り替えます。 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>既定のバッジ

既定のバッジセットは、チームのユーザーが自分のピアを作業の前後に向かって理解できるように設計されています。

![既定のバッジセットのプレビュー](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>教育機関向けのソーシャルおよび感情的な学習バッジ

教師は、ソーシャルおよび感情的ラーニング (SEL) のアチーブメントと行動のために、これらの概念を説明するバッジで個々の学生を認識することができます。

![教育機関向けのソーシャルおよび感情的ラーニングバッジのプレビュー](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>独自のバッジを作成する

[ **ユーザー設定のバッジ** ] トグルを [オン] に切り替えて、[ **カスタムバッジの作成**] を選択します。 そこから、サイドパネルでカスタムバッジを設計できます。 最大25個のカスタムバッジを作成できます。 

1. バッジ名を入力します。 これは、ユーザーが称賛を送信したときにバッジに表示される名前です。

2. バッジの色を設定します。 バッジのテキストと背景の色を設定するには、16進数の値として色を入力する必要があります。

   > [!TIP]
   > 16進値を初めて使用する場合は、この記事では、その使用方法を説明した [簡単な概要](#hex-colors-intro) を説明します。

3. バッジ画像をアップロードします。 許可されているファイルの種類はです。.PNG. 画像ファイルの最大サイズは 216 X 216 ピクセルで、40 KB 未満である必要があります。
![背景、テキスト、およびイメージフィールドのラベルが付いたバッジ](media/praise-app-badge-fields.png)

4. バッジ名をローカライズします。 [ローカライズされた **バッジ名**] で [ **追加**] を選びます。 ドロップダウンリストから目的のロケールを選択します。 次に、指定した言語でバッジ名を入力します。

5. 特定のロケールからバッジを除外します。 [ **以下のロケールからバッジを除外**] で [ **追加**] を選びます。 ドロップダウンリストから除外するロケールを選択します。

6. **[適用]** を選択します。 これで、新しいバッジがカスタムバッジテーブルに表示されるようになります。

> [!NOTE]
> 手順4と5がスキップされると、バッジはすべてのロケールの既定の言語になります。
>
> バッジの選択の変更が完了したら、必ず [ **Submit**] を選んでください。 この変更が組織で利用可能になるまでには、数時間かかることがあります。

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>16進数の値を使用して色を指定する

16進数の色の値は、特定の色の赤 (RR)、緑色 (GG)、青 (BB) の強さを、倍率 00 ~ FF で表した6桁の16進数の文字列です。 3つの色の値をすべてまとめて入力すると、16進数の値が表示されます。 #RRGGBB

たとえば、color red の16進数の値は、可能な限り最高の値、FF、緑、青のいずれかで設定されているため、最も低い値である00に設定されているため、#FF0000 ます。

さまざまな色とその16進値を調べるには、 [Bing の色の選択](https://www.bing.com/search?q=color+picker)を確認します。

使用を開始するための色の例を次に示します。

|色  |Hex 値|
|-------|---------|
|![16進数の色 #FF6666](media/hexColor1.png)|  #FF6666   |
|![16進数の色 #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![16進数の色 #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![16進数の色 #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![16進数の色 #800080](media/hexColor5.png)|  #800080   |
|![16進数の色 #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>カスタムバッジを作成するためのベストプラクティス

**すべてのバッジを一度に送信します。** 新しいバッジが処理されるまでには時間がかかるため、送信する前に、すべてのカスタムバッジをテーブルに追加することをお勧めします。

**色を選択するときは、アクセシビリティを念頭に置いてください。** 一部の色は、他の色よりも見やすくなります。  テキストと背景の色のコントラストを作成して、バッジ名を読みやすくします。 たとえば、暗い背景色を選んだ場合は、淡色テキストの色を選択します。

**画像を選択するときは、バッジの寸法を念頭に置いておきます。** 最高の品質を得るには、216 x 216 ピクセル (最大サイズ) の画像ファイルをアップロードすることをお勧めします。 これらの寸法に合わせて画像を拡大または変形しないようにします。

**バッジ画像が四角形でない場合は、画像を透明にします。** イメージファイルを称賛にアップロードする前に、この操作を行う必要があります。

![Left: 透明ではない画像を含むバッジ、右: バッジが透明な画像](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>バッジ設定アセット

組み込みのバッジセットを変更することはできません。そのため、組み込みのバッジ設定が有効になっていると、セット内のすべてのバッジが称賛アプリに追加されます。 組み込みセットから特定のバッジを追加したり、他のユーザーを脱退したりする場合は、カスタムバッジとして使用するバッジを再作成します。 次の表の組み込みセットからバッジのテキストと背景色を見つけることができます。

### <a name="default-badges-assets"></a>既定のバッジアセット

</br>

|バッジ名     |画像ファイル  |テキストの色 | 背景色 |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|すごい        |[Awesome PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Coach          |[エコノミーでの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Courage        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Creative       |[クリエイティブな PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|的      |[包括的な PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|種類のハート     |[ハートの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|優位性     |[リーダーシップの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Optimism       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|問題ソルバー |[問題のある PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|チームプレーヤー    |[チームプレーヤーの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|ありがとう      |[ありがとうございます](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>教育機関向けのソーシャルおよび感情的な学習バッジ

</br>

|バッジ名        |画像ファイル  |テキストの色 | 背景色 |
|------------------|------------|---------- |--------|
|コミュニケーション     |[コミュニケーションの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|重要な思考 |[重要な思考 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|好奇心         |[好奇心 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathy           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|ゴールのフォローアップ      |[目標のフォローアップ PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|利点        |[モチベーションの PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|ティ       |[常設 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|従っ           |[PNG を尊重する](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|業務    |[責任の PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|自己認知    |[自己認知型 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|自動管理   |[自己管理 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thoughtfulness    |[Thoughtfulness PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
