---
title: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバー上のホームユーザー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98ef5adb3fafc40e4afe02384492be4a88fd2b24
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013 の存続可能ブランチアプライアンスまたはサーバー上のホームユーザー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-10_

存続可能ブランチアプライアンスまたは存続可能ブランチサーバーでユーザーをホームにするプロセスは、フロントエンドプールでユーザーをホームにするプロセスに似ています。 中央サイトで存続可能 Branch Appliance または存続可能 Branch Server プロシージャを実行します。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>存続可能ブランチアプライアンスまたは存続可能ブランチサーバー上のホームユーザーに

1.  ユーザーを存続可能ブランチサーバーまたは存続可能ブランチサーバーに移動する前に、Lync Server 管理シェルを開き、次のすべての手順を実行します。
    
      - コマンドレット**Test-CsPstnOutboundCall**を実行して、存続可能ブランチサーバーが実行中で、公衆交換電話網 (PSTN) 接続が構成されていることを確認します。 PSTN ゲートウェイのプロパティを変更する必要がある場合は、コマンドレット**Set-CsPstnGateway**を使用してください。
    
      - **Set-csvoicepolicy**コマンドレットを実行して、存続可能ブランチサーバーに所属するユーザーが適切な VoIP ルーティングポリシーを持っていることを確認します。 VoIP ポリシーを変更する必要がある場合は、コマンドレット**set-csvoicepolicy**を使用します。
    
      - **Get-csvoicemailreroutingconfiguration**コマンドレットを実行して、ボイスメールの再ルーティング設定が構成されていることを確認します。 ボイスメールの再ルーティング設定を変更する必要がある場合は、 **get-csvoicemailreroutingconfiguration**コマンドレットを使用します。

2.  Lync Server 管理シェルで、コマンドレットを実行して、ホームユーザーを**移動します**。

<div>


> [!NOTE]  
> また、Lync Server コントロールパネルを使用して、前提条件とホームユーザーを確認することもできます。



</div>

<div>


> [!NOTE]  
> Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

