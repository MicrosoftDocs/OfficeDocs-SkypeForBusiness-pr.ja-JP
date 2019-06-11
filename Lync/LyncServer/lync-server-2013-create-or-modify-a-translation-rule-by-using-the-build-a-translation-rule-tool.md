---
title: 翻訳ルールツールを使って翻訳ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f498af25dfd851bd2950ce08d5c66179b95ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Lync Server 2013 の翻訳ルールの作成ツールを使用して、翻訳ルールを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

翻訳ルールを定義する場合は、次の手順に従います。**翻訳**ルールツールで一連の値を入力し、Lync Server コントロールパネルを有効にして、対応する照合パターンと翻訳ルールを生成することができます。 または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。 詳細について[は、「Lync Server 2013 で翻訳ルールを手動で作成または変更](lync-server-2013-create-or-modify-a-translation-rule-manually.md)する」を参照してください。

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>変換ルールの構築ツールを使用してルールを定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  翻訳ルールの定義を開始するには、「 [Lync server 2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)する」を参照するか、「 [lync server 2013 でメディアをバイパスしないトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する」の手順に従ってください。

4.  [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。

5.  (オプション) [**説明**] に、「**US International long-distance dialing**」などの変換ルールの説明を入力します。

6.  ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。
    
      - [**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。 たとえば、このフィールド**+** に「e.i」形式の数値 (+ で始まる) を入力します。
    
      - [**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。たとえば、**11** と入力してドロップダウン リストで [**At least** ] を選択すると、最低でも 11 桁の長さの番号に一致します。
    
      - [**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。 たとえば、「 **1** 」と入力すると**+** 、番号の最初からが取り除かれます。
    
      - [**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「**011**」と入力します。
    
    これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。
    
    **^\\+ (\\d{9}\\d +) $**
    
    [**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。このパターンには、次の 2 つのパーツがあります。
    
      - 一致パターンの桁数を表す値 (**$1** など)
    
      - (オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値
    
    上述の例の値を使用した場合、[**変換ルール**] フィールドに **011$1** が表示されます。
    
    この変換ルールを適用すると、+441235551010 が 011441235551010 になります。

7.  [**OK**] をクリックして変換ルールを保存します。

8.  [**OK**] をクリックしてトランク構成を保存します。

9.  [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > 変換ルールを作成または変更したときは必ず、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で翻訳ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でメディアをバイパスせずにトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

