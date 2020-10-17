---
title: 'Lync Server 2013: 手動で正規化ルールを作成または変更する'
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
ms.openlocfilehash: 58cd29feeeb34646a7d4a27ef78064d692f9ffa0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525844"
---
# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Lync Server 2013 で正規化ルールを手動で作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-22_

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。 Lync Server コントロールパネルの [正規化ルールの構築] を使用して正規化ルールを作成または変更する場合は、「 [create a 正規化 rule in Using Lync server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)」を参照してください。

<div>

## <a name="to-define-a-normalization-rule-manually"></a>正規化ルールを手動で定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  オプション「 [Create a dial plan In Lync server 2013](lync-server-2013-create-a-dial-plan.md) 」または「 [Modify a Dial Plan in lync server 2013](lync-server-2013-modify-a-dial-plan.md)」の手順を実行します。

4.  [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。

5.  (オプション) [**説明**] フィールドに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。

6.  [**正規化ルールの構築**] で [**編集**] をクリックします。

7.  [**正規表現の入力**] で次のように入力します。
    
      - [**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    
      - [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。
    
    たとえば、[**このパターンを照合**] に「 **^ ( \\ d {7} ) $** 」と入力し、[**変換ルール**] に「 **+ 1425 $ 1** 」と入力すると、ルールは5550100から + 14255550100 に正規化されます。

8.  (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。

9.  (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。
    
    <div>
    

    > [!NOTE]  
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。

    
    </div>

10. [**OK**] をクリックして正規化ルールを保存します。

11. [**OK**] をクリックしてダイヤル プランを保存します。

12. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 正規化ルールを作成または変更するときにはいつでも、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A> 」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[「Lync Server 2013 で正規化ルールを構築する」を使用して正規化ルールを作成または変更する](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

