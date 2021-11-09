---
title: 呼び出された ID プレゼンテーションの翻訳ルールを作成または変更Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '概要: 翻訳ルールの作成ツールを使用して翻訳ルールを定義する方法についてSkype for Business Server。'
ms.openlocfilehash: 82e737ddcd7ed7c17de3cdd968d31996e50074be
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864434"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>呼び出された ID プレゼンテーションの翻訳ルールを作成または変更Skype for Business Server

**概要:**[翻訳ルールの作成] ツールを使用して翻訳ルールを定義する方法については、Skype for Business Server。

変換ルールの作成ツールに値のセットを入力し、Skype for Business Server コントロール パネルで対応する一致パターンと変換ルールを生成して、変換ルールを定義する場合は、次の手順を実行します。 または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。 詳細については、「[Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)」を参照してください。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>変換ルールの構築ツールを使用してルールを定義するには

1. [コントロール Skype for Business Server] を開きます。

2. 変換ルールの定義を開始するには、「Skype for Business Server ~ 手順 10 でメディア バイパスを使用してトランクを構成する」または[「Skype for Business Server](configure-trunk-with-media-bypass.md)から手順 9 まででメディア バイパスのないトランクを構成する」[の手順に](configure-trunk-without-media-bypass.md)従います。

3. [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。

4. (省略可能)[ **説明]** に、翻訳ルールの説明 (米国国際長距離ダイヤルなど) を入力します。

5. ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。

   - [**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。 たとえば、+ で開始される E.164 形式の番号に一致させるには、このフィールドに「+」を入力します。

   - [**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。 たとえば、11 と入力し、少なくとも 11 桁の数字と一致するドロップダウン リストで [At] を選択します。

   - [**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。 たとえば、数値の先頭から+ を削除するには、1 と入力します。

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
   > 変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメントの「音声ルーティング構成[に](voice-route-config-changes.md)保留中の変更Skype for Businessを発行する」を参照してください。

### <a name="to-define-a-translation-rule-manually"></a>変換ルールを手動で定義するには

1. [Skype for Business Server] コントロール パネルを開く

2. 変換ルールの定義を開始するには、「Skype for Business Server ~ 手順 10 でメディア バイパスを使用してトランクを構成する」または[「Skype for Business Server](configure-trunk-with-media-bypass.md)から手順 9 まででメディア バイパスのないトランクを構成する」[の手順に](configure-trunk-without-media-bypass.md)従います。

3. [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。

4. (省略可能)[ **説明**] に、翻訳ルールの説明を入力します 。たとえば、US International 長距離ダイヤル。

5. [**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。

6. [**正規表現の入力**] に、次のように入力します。

   - [**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。

   - [**変換ルール**] に、変換される番号の形式のパターンを指定します。

     たとえば、[このパターンの一致] に ^ (\d \d+)$ を入力し、変換ルールに \+ {9} 011$1を入力すると、+441235551010 が 011441235551010 に変換されます。

7. [**OK**] をクリックして変換ルールを保存します。

8. [**OK**] をクリックしてトランク構成を保存します。

9. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。

    > [!NOTE]
    > 変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメントの「音声ルーティング構成[に](voice-route-config-changes.md)保留中の変更Skype for Businessを発行する」を参照してください。

## <a name="see-also"></a>関連項目

[メディア バイパスを使用してトランクを構成Skype for Business Server](configure-trunk-with-media-bypass.md)

[メディア バイパスを使用せずにトランクを構成Skype for Business Server](configure-trunk-without-media-bypass.md)

[音声ルーティング構成に保留中の変更を公開Skype for Business](voice-route-config-changes.md)

[メディア バイパスを展開Skype for Business Server](deploy-media-bypass.md)