---
title: 'Lync Server 2013: 手動による正規化ルールの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Lync Server 2013 での手動による正規化ルールの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-22_

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。 Lync Server コントロールパネルで [正規化ルールの作成] を使用して正規化ルールを作成または変更する場合は、「 [Lync server 2013 で正規化ルールを作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)する」を参照してください。

<div>

## <a name="to-define-a-normalization-rule-manually"></a>正規化ルールを手動で定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  省略「 [Lync server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」または「 [lync server 2013 でダイヤルプランを変更](lync-server-2013-modify-a-dial-plan.md)する」の手順を実行します。

4.  [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号パターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。

5.  (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。

6.  [**正規化ルールの構築**] で [**編集**] をクリックします。

7.  [**正規表現の入力**] で次のように入力します。
    
      - [**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    
      - [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。
    
    たとえば、**このパターンに一致**する **^\\({7}d) $** と、**翻訳ルール**の **+ 1425 $ 1**を入力すると、ルールは5550100から + 14255550100 に正規化されます。

8.  (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。

9.  (オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。
    
    <div>
    

    > [!NOTE]  
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。

    
    </div>

10. [**OK**] をクリックして正規化ルールを保存します。

11. [**OK**] をクリックしてダイヤル プランを保存します。

12. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 正規化ルールを作成または変更するときにはいつでも、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[「Lync Server 2013 で正規化ルールを作成する」を使用して正規化ルールを作成または変更する](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

