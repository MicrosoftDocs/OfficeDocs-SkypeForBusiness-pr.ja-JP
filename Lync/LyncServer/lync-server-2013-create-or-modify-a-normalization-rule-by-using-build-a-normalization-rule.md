---
title: 正規化ルールの構築を使用して正規化ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d4c6d5b8a8cd53cee9fdae0a38769a535b118
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508844"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>「Lync Server 2013 で正規化ルールを構築する」を使用して正規化ルールを作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server コントロールパネルで正規化ルールを作成または変更するには、次の手順を実行します。 または、手動で正規化ルールを作成または変更する場合は、「 [Lync Server 2013 で手動で正規化ルールを作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)する」を参照してください。

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>[正規化ルールの構築] を使用してルールを定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  オプション「 [Create a dial plan In Lync server 2013](lync-server-2013-create-a-dial-plan.md) 」または「 [Modify a Dial Plan in lync server 2013」](lync-server-2013-modify-a-dial-plan.md) ~ 手順10の手順を実行します。

4.  [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。

5.  (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。

6.  [**正規化ルールの構築**] で、次のフィールドに値を入力します。
    
      - **開始番号**    オプションパターンと照合するダイヤル番号の先頭の桁数を指定します。 たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。
    
      - **長さ**    照合パターンで桁数を指定し、パターンがこの長さと正確に一致するようにするか、または少なくともこの長さのダイヤル番号に一致するか、または任意の長さのダイヤル番号に一致するかを選択します。
    
      - **削除**     する数字オプションパターンと照合するダイヤル番号から削除する開始番号の数字を指定します。
    
      - **追加**     する数字オプションパターンと照合するダイヤル番号に追加する数字を指定します。
    
    これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。 たとえば、[**開始桁の数字**] を空にして [**長さ**] フィールドに「**7**」と入力し、[**完全一致**] を選択し、[**削除する桁数**] で「**0**」と指定すると、[**一致パターン**] に表示される正規表現は次のようになります。
    
    **^ ( \\ d {7} ) $**

7.  [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    
      - 一致パターンで指定した桁数を表す値。 たとえば、一致パターンが **^ ( \\ d {7} ) $** の場合、変換ルールの **$1** は7桁のダイヤル番号を表します。
    
      - (オプション) [**追加する数字**] フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。
    
    たとえば、 **宛先に一致するパターンに** **^ ( \\ d {7} ) $** が含まれている場合、ダイヤル番号と **変換ルール** には、e.164 電話番号のパターンとして **+ 1425 $ 1** が含まれます。このルールは5550100から + 14255550100 を正規化します。

8.  (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。

9.  (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。
    
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


[Lync Server 2013 で正規化ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
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

