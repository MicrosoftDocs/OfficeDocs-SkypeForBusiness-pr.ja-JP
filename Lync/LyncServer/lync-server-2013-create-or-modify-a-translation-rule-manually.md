---
title: 'Lync Server 2013: 変換ルールを手動で作成または変更する'
description: 'Lync Server 2013: 変換ルールを手動で作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f393ca1983e072090cc27d47b142dace8b566c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574503"
---
# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Lync Server 2013 で変換ルールを手動で作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-06_

一致するパターンおよび変換ルールの正規表現を書いて変換ルールを定義する場合は、次の手順を実行します。 または、[ **変換ルールの構築** ] ツールに値のセットを入力し、Lync Server コントロールパネルを有効にして、対応する一致パターンと変換ルールを生成することもできます。 詳細については、「 [Lync Server 2013 の変換ルールの構築ツールを使用して変換ルールを作成または変更](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)する」を参照してください。

<div>

## <a name="to-define-a-translation-rule-manually"></a>変換ルールを手動で定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  変換ルールの定義を開始するには、「 [lync server 2013 でのメディアバイパスを使用](lync-server-2013-configure-a-trunk-with-media-bypass.md) したトランクの構成」の手順10まで、または「 [lync server 2013 でのメディアバイパスを使用しないトランクの構成](lync-server-2013-configure-a-trunk-without-media-bypass.md) 」の手順9に記載されている手順を実行します。

4.  [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。

5.  (省略可能) [**説明**] に、「**米国長距離国際電話ダイヤル**」など、変換ルールの説明を入力します。

6.  [**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。

7.  [**正規表現の入力**] に、次のように入力します。
    
      - [**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。
    
      - [**変換ルール**] に、変換される番号の形式のパターンを指定します。
    
    たとえば、[**このパターンを照合**] に「 ** ^ \\ + ( \\ d {9} \\ d +) $** 」と入力し、[**変換ルール**] に「 **011 $ 1** 」と入力すると、ルールは + 441235551010 から011441235551010に変換されます。

8.  [**OK**] をクリックして変換ルールを保存します。

9.  [**OK**] をクリックしてトランク構成を保存します。

10. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 変換ルールを作成または変更したときは必ず、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A> 」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で変換ルールの構築ツールを使用して変換ルールを作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
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

