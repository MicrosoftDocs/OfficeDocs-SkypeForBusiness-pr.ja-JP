---
title: Skype for Business Server で呼び出し ID プレゼンテーションの変換ルールを作成または変更する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '概要: Skype for Business Server で変換ルールの作成ツールを使用して変換ルールを定義する方法について説明します。'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804197"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Skype for Business Server で呼び出し ID プレゼンテーションの変換ルールを作成または変更する

**概要:** Skype for Business Server の変換ルールの作成ツールを使用して変換ルールを定義する方法について説明します。

変換ルールの作成ツールに値のセットを入力し、Skype for Business  Server コントロール パネルを有効にし、対応する一致パターンと変換ルールを生成することで、変換ルールを定義する場合は、次の手順を実行します。 または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。 詳細については、「[Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)」を参照してください。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>変換ルールの構築ツールを使用してルールを定義するには

1. Skype for Business Server コントロール パネルを開きます。

2. 変換ルールの定義を開始するには [、「Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10」または [「Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9」の手順に従います。

3. [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。

4. (省略可能)[ **説明]** に、変換ルールの説明 (米国国際長距離ダイヤルなど) を入力します。

5. ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。

   - [**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。 たとえば、+ で開始される E.164 形式の番号に一致させるには、このフィールドに「+」を入力します。

   - [**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。 たとえば、ドロップダウン リストで 11 を入力し、少なくとも 11 桁の数字と一致する数値を選択します。

   - [**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。 たとえば、「1」と入力すると、数値の先頭から + が取り除かされます。

   - [**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。 たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「011」と入力します。

     これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。 たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。

     ^\+(\d {9} \d+)$

     [**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。 このパターンには、次の 2 つのパーツがあります。

   - 一致パターンの桁数を表す値 ($1 など)

   - (オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値

     上述の例の値を使用した場合、[変換ルール] フィールドに **011$1** が表示されます。

     この変換ルールを適用すると、+441235551010 が 011441235551010 になります。

6. [**OK**] をクリックして変換ルールを保存します。

7. [**OK**] をクリックしてトランク構成を保存します。

8. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。

   > [!NOTE]
   > 変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。

### <a name="to-define-a-translation-rule-manually"></a>変換ルールを手動で定義するには

1. Skype for Business Server コントロール パネルを開く

2. 変換ルールの定義を開始するには [、「Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10」または [「Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9」の手順に従います。

3. [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。

4. (省略可能)[ **説明]** に、変換ルールの説明 (米国国際長距離ダイヤルなど) を入力します。

5. [**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。

6. [**正規表現の入力**] に、次のように入力します。

   - [**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。

   - [**変換ルール**] に、変換される番号の形式のパターンを指定します。

     たとえば、Match this pattern に ^ (\d \d+)$ を入力し、変換ルールに 1 ドルを入力すると、ルールは \+ {9} +441235551010 を 011441235551010に変換します。

7. [**OK**] をクリックして変換ルールを保存します。

8. [**OK**] をクリックしてトランク構成を保存します。

9. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。

    > [!NOTE]
    > 変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。

## <a name="see-also"></a>関連項目

[Skype for Business Server でメディア バイパスを使用してトランクを構成する](configure-trunk-with-media-bypass.md)

[Skype for Business Server でメディア バイパスを使用せずにトランクを構成する](configure-trunk-without-media-bypass.md)

[Skype for Business での音声ルーティング構成に対する保留中の変更の公開](voice-route-config-changes.md)

[Skype for Business Server でのメディア バイパスの展開](deploy-media-bypass.md)

