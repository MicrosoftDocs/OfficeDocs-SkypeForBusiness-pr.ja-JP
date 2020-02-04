---
title: 正規化ルールを作成または変更する
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
ms.openlocfilehash: 519d4d8ee00e0922d40155c541b0f869df095ab1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>「Lync Server 2013 で正規化ルールを作成する」を使用して正規化ルールを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server コントロールパネルで正規化ルールを作成または変更する場合は、次の手順を実行します。 または、手動で正規化ルールを作成または変更する場合は、「 [Lync Server 2013 で正規化ルールを手動で作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)する」を参照してください。

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>正規化ルールを作成してルールを定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  省略「 [Lync server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」または「手順10でダイヤルプランを作成する」の手順に従って、「 [lync server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

4.  [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号パターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。

5.  (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。

6.  [**正規化ルールの構築**] で、次のフィールドに値を入力します。
    
      - **先頭の数字**   (省略可能) パターンに一致させるダイヤル番号の先頭の数字を指定します。 たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。
    
      - **[長さ**   ] 一致するパターンの桁数を指定し、パターンをこの長さと正確に一致させるか、またはダイヤルした電話番号に一致するかどうかを選択します。
    
      - **[削除**   する数字] (省略可能) パターンの対象となるダイヤル番号から削除する開始番号の数を指定します。
    
      - **追加する数字**   (省略可能) パターンと一致させるダイヤル番号に追加する数字を指定します。
    
    これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。たとえば、[**開始桁数**] を空にして "**長さ**" フィールドに「**7**」と入力し、[**完全一致**] を選択し、[**削除する桁数**] で「**0**」と指定すると、[**一致パターン**] に表示される正規表現は次のようになります。
    
    **^ (\\d{7}) $**

7.  [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    
      - 一致パターンで指定した桁数を表す値。 たとえば、対応するパターンが **^ (\\d{7}) $** の場合、翻訳ルールの **$1**では、7桁のダイヤル番号が示されます。
    
      - (オプション) "**追加する数字**" フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。
    
    たとえば、**一致するパターンに** **^ (\\d{7}) $** が含まれている場合、ダイヤル番号のパターンと**翻訳ルール**に **+ 1425 $ 1**が含まれていると、ルールは5550100から + 14255550100 を正規化します。

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


[Lync Server 2013 での手動による正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
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

