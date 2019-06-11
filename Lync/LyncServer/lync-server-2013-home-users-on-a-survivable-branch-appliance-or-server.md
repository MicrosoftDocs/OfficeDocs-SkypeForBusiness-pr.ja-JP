---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-10_

Survivable Branch Appliance または Survivable ブランチサーバーにユーザーをホームするプロセスは、フロントエンドプールでユーザーをホームにするプロセスと似ています。 セントラルサイトで Survivable Branch Appliance または Survivable Branch Server の手順を実行します。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Survivable Branch Appliance または Survivable ブランチサーバー上のホームユーザーに

1.  Survivable Branch Server または Survivable ブランチサーバーにユーザーを移動する前に、Lync Server 管理シェルを開き、次のすべての操作を行います。
    
      - コマンドレット**テスト-CsPstnOutboundCall**を実行して、Survivable Branch Server が実行されていて、公衆交換電話網 (PSTN) 接続が構成されていることを確認します。 PSTN ゲートウェイのプロパティを変更する必要がある場合は、コマンドレットのセットされた**CsPstnGateway**を使用します。
    
      - **CsVoicePolicy**コマンドレットを実行して、Survivable ブランチサーバーをホームにしているユーザーに適切な VoIP ルーティングポリシーが設定されていることを確認します。 VoIP ポリシーを変更する必要がある場合は、コマンドレット**CsVoicePolicy**を使用します。
    
      - **CsVoicemailReroutingConfiguration**コマンドレットを実行して、ボイスメールの再ルーティング設定が構成されていることを確認します。 ボイスメールの再ルーティング設定を変更する必要がある場合は、コマンドレット**CsVoicemailReroutingConfiguration**を使用します。

2.  Lync Server 管理シェルでコマンドレットを実行し**** て、ホームユーザーを移動します。

<div>


> [!NOTE]  
> Lync Server コントロールパネルを使用して、前提条件とホームユーザーを確認することもできます。



</div>

<div>


> [!NOTE]  
> Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

