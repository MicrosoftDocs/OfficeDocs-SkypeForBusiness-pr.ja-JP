---
title: 'Lync Server 2013: 翻訳ルールを手動で作成または変更する'
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
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Lync Server 2013 で翻訳ルールを手動で作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-06_

一致するパターンと翻訳ルールの正規表現を作成して、翻訳ルールを定義する場合は、次の手順に従います。 または、[**翻訳ルール**ツールのビルド] ツールで一連の値を入力し、Lync Server コントロールパネルを有効にして、対応する照合パターンと翻訳ルールを生成することもできます。 詳細については、「 [Lync Server 2013 の翻訳ルールの作成ツールを使用して、翻訳ルールを作成または変更](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)する」を参照してください。

<div>

## <a name="to-define-a-translation-rule-manually"></a>変換ルールを手動で定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  翻訳ルールの定義を開始するには、「 [Lync server 2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)する」を参照するか、「 [lync server 2013 でメディアをバイパスしないトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する」の手順に従ってください。

4.  [**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。

5.  (オプション) [**説明**] に、「**US International long-distance dialing**」など、変換ルールの説明を入力します。

6.  [**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。

7.  [**正規表現の入力**] で次のように入力します。
    
      - [**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。
    
      - [**変換ルール**] に、変換される番号の形式のパターンを指定します。
    
    たとえば、「 ** ^ \\+\\{9}\\(d d +) $** 」と入力すると (**このパターン**と**011 $ 1**の**翻訳ルール**が適用されます)、ルールは + 441235551010 から011441235551010に変換されます。

8.  [**OK**] をクリックして変換ルールを保存します。

9.  [**OK**] をクリックしてトランク構成を保存します。

10. [**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 変換ルールを作成または変更したときは必ず、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の翻訳ルールの作成ツールを使用して、翻訳ルールを作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
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

