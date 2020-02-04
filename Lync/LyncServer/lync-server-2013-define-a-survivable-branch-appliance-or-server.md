---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-07_

トポロジに Survivable Branch アプライアンスまたはサーバーを追加したときに定義していない場合は、セントラルサイトでこの手順を実行します。

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Survivable Branch Appliance または Survivable Branch Server を定義するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  コンソールツリーで、[セントラルサイト]、[**ブランチサイト**] の順に展開して、Survivable branch Appliance または Survivable branch Server の展開を計画しているブランチサイトの名前を展開します。

3.  **Survivable Branch**Appliance を右クリックし、[ **New Survivable branch Appliance**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable Branch アプライアンス</STRONG>では、Survivable branch Servers と Survivable branch アプライアンスを定義しています。

    
    </div>

4.  [ **Survivable Branch appliance の定義**] ダイアログボックスで、[ **fqdn**] をクリックし、このブランチサイトで展開する Survivable Branch Appliance または Survivable branch Server の完全修飾ドメイン名 (FQDN) を入力して、[**次へ**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > Survivable Branch Appliance を定義する場合、 <STRONG>FQDN</STRONG>で入力する名前は、 <STRONG>servicePrincipalName</STRONG>属性に割り当てた Survivable Branch Appliance FQDN と同じである必要があります。 詳細については、「 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Lync Server 2013 の Active Directory に Survivable Branch Appliance を追加する</A>」を参照してください。

    
    </div>

5.  [**フロントエンドプール**] をクリックし、この Survivable branch server が接続するセントラルサイトのフロントエンドサーバー (ユーザーサービスプール) をクリックして、[**次へ**] をクリックします。

6.  [ **Edge server**] をクリックし、この Survivable branch Appliance または Survivable branch Server が接続するエッジプールをクリックして、ブランチサイトのリモートユーザーに PSTN 接続を提供してから、[**次へ**] をクリックします。

7.  [**ゲートウェイの fqdn または Ip アドレス**] をクリックして、着信または発信の PSTN 通話をルーティングするために、Survivable branch Appliance または Survivable ブランチサーバーが関連付けられているゲートウェイピアの FQDN または ip アドレスを入力します。
    
    <div>
    

    > [!IMPORTANT]  
    > Survivable Branch Appliance を定義している場合、これは、Survivable Branch アプライアンス内の仲介サーバーが PSTN 接続用に接続するゲートウェイです。

    
    </div>

8.  [ **IP/PSTN ゲートウェイのリスニングポート**] をクリックし、既定のポートを受け入れます。

9.  [ **Sip トランスポートプロトコル**] で、Survivable branch Appliance または Survivable branch Server で使用するトランスポートプロトコルをクリックし、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由から、トランスポート層セキュリティ (TLS) を使用することを強くお勧めします。 Survivable Branch appliance を定義する場合は、Survivable Branch Appliance のベンダーのドキュメントを参照して、Survivable Branch Appliance が TLS プロトコルをサポートしていることを確認してください。

    
    </div>

10. コンソールツリーで、新しい Survivable ブランチアプライアンスまたはサーバーを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。

**次のステップ**: [Lync Server 2013-ブランチサイトタスクを使用して Survivable Branch Appliance または server を展開する](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

