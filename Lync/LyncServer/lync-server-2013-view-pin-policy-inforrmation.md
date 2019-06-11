---
title: 'Lync Server 2013: PIN ポリシーの inforrmation を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad912c4442a243beaaa4410d8931f0940d743177
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Lync Server 2013 で PIN ポリシーの inforrmation を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

[ **Pin ポリシー** ] タブを使って、IP 電話で Lync 2013 に接続しているユーザーの暗証番号 (pin) の認証を表示できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。 詳細については、「 [Lync Server 2013 で既存の Web サービスの構成の設定を変更](lync-server-2013-modify-existing-web-service-configuration-settings.md)する」を参照してください。

ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Lync Server コントロールパネルの PIN ポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。

4.  [**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した PIN ポリシーの表示

Windows PowerShell と CsPinPolicy コマンドレットを使用して、PIN ポリシーを表示することもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-pin-policies"></a>PIN ポリシーを表示するには

  - すべての PIN ポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsPinPolicy
    
    次のような情報が表示されます。
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

詳細については、 [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で既存の Web サービス構成の設定を変更する](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Lync Server 2013 で新しい PIN ポリシーを作成する](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

