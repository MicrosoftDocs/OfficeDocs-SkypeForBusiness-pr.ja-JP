---
title: 'Lync Server 2013: ユーザーのコールパークを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528784"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Lync Server 2013 でユーザーのコールパークを有効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-11_

ユーザーは、音声ポリシーのコールパークが有効になるまで、通話をパークしたり保留された通話を取得したりすることはできません。

<div>


> [!NOTE]  
> 既定では、すべてのユーザーに対してコールパークが無効になります。



</div>

通話パークは、グローバルスコープまたはサイトスコープまたはユーザースコープで有効にすることができます。 ユーザースコープはサイトスコープより優先され、サイトスコープはグローバルスコープより優先されます。 複数の音声ポリシーがある場合は、グローバルポリシーだけでなく、すべてのポリシーを確認してコールパークを有効にします。

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Lync Server コントロールパネルを使用してユーザーのコールパークを有効にするには

1.  **RTCUniversalServerAdmins**グループのメンバーとして、または**CsVoiceAdministrator**、 **Csserveradministrator**、または**csadministrator**管理者役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [ **音声ポリシー** ] タブをクリックします。

5.  既存の音声ポリシーをダブルクリックして、[ **音声ポリシーの編集** ] ダイアログボックスを開きます。

6.  [ **通話機能**] の [ **コールパークを有効にする**] を選択します。

7.  [ **OK]** をクリックして音声ポリシーを保存します。

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>コマンドレットを使用してユーザーのコールパークを有効にするには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    たとえば、既定のグローバル音声ポリシーのコールパークを有効にするには、次のようにします。
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

