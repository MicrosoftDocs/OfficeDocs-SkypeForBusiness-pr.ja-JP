---
title: 'Lync Server 2013: ユーザーのコールパークを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16538ba00571c429493a2bc0ce1ef14b0a331305
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Lync Server 2013 のユーザーに対してコールパークを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-11_

ユーザーは、音声ポリシーでのコールパークが有効になるまで、通話をパークしたり、保留中の通話を取得したりすることはできません。

<div>


> [!NOTE]  
> 既定では、すべてのユーザーに対して [コールパーク] が無効になっています。



</div>

グローバルスコープまたはサイトのスコープまたはユーザーの範囲で、通話パークを有効にすることができます。 ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。 複数のボイスポリシーがある場合は、グローバルポリシーだけでなく、すべてのポリシーを確認してコールパークを有効にします。

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Lync Server コントロールパネルを使用してユーザーのコールパークを有効にするには

1.  **RTCUniversalServerAdmins** グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**音声ポリシー**] タブをクリックします。

5.  既存の音声ポリシーをダブルクリックして、[**音声ポリシーの編集**] ダイアログ ボックスを開きます。

6.  [**通話機能**] の [**コール パークを有効にする**] を選択します。

7.  [**OK**] をクリックして音声ポリシーを保存します。

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>コマンドレットを使用してユーザーのコールパークを有効にするには

1.  RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    たとえば、既定のグローバルボイスポリシーのコールパークを有効にするには、次のようにします。
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成する](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

