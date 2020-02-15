---
title: 変換ルールの構築ツールを使用して変換ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8321603c699fb0f25fc0a3a1b94e8b216761c6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Lync Server 2013 で変換ルールの構築ツールを使用して変換ルールを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

[**変換ルールの構築**] ツールに値のセットを入力し、Lync Server コントロールパネルを有効にして対応する一致パターンと変換ルールを生成することによって、変換ルールを定義するには、次の手順を実行します。 または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。 詳細については、「 [Lync Server 2013 で変換ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-manually.md)」を参照してください。

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>変換ルールの構築ツールを使用してルールを定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  変換ルールの定義を開始するには、「 [lync server 2013 でのメディアバイパスを使用](lync-server-2013-configure-a-trunk-with-media-bypass.md)したトランクの構成」の手順10まで、または「 [lync server 2013 でのメディアバイパスを使用しないトランクの構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)」の手順9に記載されている手順を実行します。

4.  [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。

5.  (オプション) [**説明**] に、「**米国長距離国際電話ダイヤル**」などの変換ルールの説明を入力します。

6.  ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。
    
      - [**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。 たとえば、このフィールド**+** に「e.164」形式の番号 (+ で始まる) を入力します。
    
      - [**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。 たとえば、**[11]** と入力してドロップダウン リストで **[最少]** を選択すると、最低でも 11 桁の長さの番号に一致されます。
    
      - [**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。 たとえば、「 **1** 」と入力して**+** 、を番号の先頭から削除します。
    
      - [**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。 たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「**011**」と入力します。
    
    これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。 たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。
    
    **^\\+ (\\d{9}\\d +) $**
    
    [**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。 このパターンには、次の 2 つのパーツがあります。
    
      - 一致パターンの桁数を表す値 (**$1** など)
    
      - (オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値
    
    上述の例の値を使用した場合、[**変換ルール**] フィールドに **011$1** が表示されます。
    
    この変換ルールを適用すると、+441235551010 が 011441235551010 になります。

7.  [**OK**] をクリックして変換ルールを保存します。

8.  [**OK**] をクリックしてトランク構成を保存します。

9.  [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > 変換ルールを作成または変更したときは必ず、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で変換ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Lync Server 2013 でメディアバイパスを使用してトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

