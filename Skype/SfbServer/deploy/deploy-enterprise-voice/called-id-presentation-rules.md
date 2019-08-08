---
title: Skype for Business Server で呼び出された ID プレゼンテーションの翻訳ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '概要: Skype for Business Server の翻訳ルールの作成ツールを使用して、翻訳ルールを定義する方法について説明します。'
ms.openlocfilehash: 3c72e53044abe44660423bbd9bc1adbbeed2a3ed
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233785"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Skype for Business Server で呼び出された ID プレゼンテーションの翻訳ルールを作成または変更する

**概要:** Skype for Business Server の翻訳ルールの作成ツールを使用して、翻訳ルールを定義する方法について説明します。

翻訳ルールを定義する場合は、次の手順に従います。**翻訳**ルールツールで値のセットを入力し、Skype For Business Server コントロールパネルを有効にすると、対応する一致パターンと翻訳ルールが生成されます。 または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。 詳細については、「[Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)」を参照してください。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>変換ルールの構築ツールを使用してルールを定義するには

1. Skype for Business Server コントロールパネルを開きます。

2. 翻訳ルールの定義を開始するには、「 [skype For Business server でメディアバイパスを使用してトランクを構成](configure-trunk-with-media-bypass.md)する」を参照するか、手順9から[Skype for business server でメディアバイパスを構成](configure-trunk-without-media-bypass.md)します。

3. [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。

4. 省略[**説明**] に、翻訳ルールの説明を入力します (例: 米国国際長距離電話)。

5. ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。

   - [**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。 たとえば、+ で開始される E.164 形式の番号に一致させるには、このフィールドに「+」を入力します。

   - [**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。 たとえば、11桁以上の数字を一致させるには、「11」と入力し、ドロップダウンリストで少なくとも1つを選択します。

   - [**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。 たとえば、「1」と入力すると、番号の先頭から + が取り除かれます。

   - [**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。 たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「011」と入力します。

     これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。

     ^\+(\d{9}\d +) $

     [**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。 このパターンには、次の 2 つのパーツがあります。

   - 一致パターンの桁数を表す値 ($1 など)

   - (オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値

     上述の例の値を使用した場合、[変換ルール] フィールドに **011$1** が表示されます。

     この変換ルールを適用すると、+441235551010 が 011441235551010 になります。

6. [**OK**] をクリックして変換ルールを保存します。

7. [**OK**] をクリックしてトランク構成を保存します。

8. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。

   > [!NOTE]
   > 変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。

### <a name="to-define-a-translation-rule-manually"></a>変換ルールを手動で定義するには

1. Skype for Business Server コントロールパネルを開く

2. 翻訳ルールの定義を開始するには、「 [skype For Business server でメディアバイパスを使用してトランクを構成](configure-trunk-with-media-bypass.md)する」を参照するか、手順9から[Skype for business server でメディアバイパスを構成](configure-trunk-without-media-bypass.md)します。

3. [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。

4. 省略[**説明**] に、翻訳ルールの説明を入力します (例: 米国国際長距離電話)。

5. [**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。

6. [**正規表現の入力**] で次のように入力します。

   - [**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。

   - [**変換ルール**] に、変換される番号の形式のパターンを指定します。

     \+たとえば、"^ (\d{9}\d +) $" と入力すると、**翻訳ルール**の and011 $ 1 というパターンになります。**この**ルールは、+ 441235551010 から011441235551010に翻訳されます。

7. [**OK**] をクリックして変換ルールを保存します。

8. [**OK**] をクリックしてトランク構成を保存します。

9. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。

    > [!NOTE]
    > 変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Skype for Business Server でメディアバイパスを使用してトランクを構成する](configure-trunk-with-media-bypass.md)

[Skype for Business Server でメディアをバイパスせずにトランクを構成する](configure-trunk-without-media-bypass.md)

[Skype for Business の音声ルーティング構成に保留中の変更を公開する](voice-route-config-changes.md)

[Skype for Business Server でメディアバイパスを展開する](deploy-media-bypass.md)

