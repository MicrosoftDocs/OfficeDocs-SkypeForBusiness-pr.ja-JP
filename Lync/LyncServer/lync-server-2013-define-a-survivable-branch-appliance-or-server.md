---
title: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバーの定義'
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
ms.openlocfilehash: 329fae20f239f10583b83b64d9b78fa953f6cdc3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-07_

存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーをトポロジに追加した際にこれを定義しなかった場合は、この手順をセントラル サイトで実行します。

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>存続可能 Branch Appliance または存続可能ブランチサーバーを定義するには

1.  [**スタート**]、[**すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server トポロジビルダー**] の順にクリックします。

2.  コンソールツリーでセントラルサイトを展開し、[**ブランチサイト**] を展開して、存続可能 branch Appliance または存続可能 branch Server の展開を計画しているブランチサイトの名前を展開します。

3.  [**存続可能 Branch**Appliance] を右クリックし、[ **New 存続可能 branch Appliance**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>存続可能 Branch アプライアンス</STRONG>では、存続可能ブランチサーバーと存続可能ブランチアプライアンスを定義します。

    
    </div>

4.  [**存続可能ブランチアプライアンスの定義**] ダイアログボックスで、[ **fqdn**] をクリックし、このブランチサイトで展開する存続可能 Branch Appliance または存続可能ブランチサーバーの完全修飾ドメイン名 (fqdn) を入力して、[**次へ**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > 存続可能ブランチアプライアンスを定義している場合は、[ <STRONG>FQDN</STRONG> ] に入力する名前は、 <STRONG>servicePrincipalName</STRONG>属性に割り当てた存続可能 Branch Appliance FQDN と同じである必要があります。 詳細については、「 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a 存続可能 Branch Appliance To Active Directory In Lync Server 2013</A>」を参照してください。

    
    </div>

5.  [**フロントエンドプール**] をクリックし、この存続可能 branch Appliance または存続可能 branch server が接続するセントラルサイトのフロントエンドサーバー (ユーザーサービスプール) をクリックして、[**次へ**] をクリックします。

6.  [**エッジサーバー**] をクリックし、この存続可能 branch Appliance または存続可能ブランチサーバーが接続するエッジプールをクリックして、ブランチサイトのリモートユーザーに PSTN 接続を提供し、[**次へ**] をクリックします。

7.  [**ゲートウェイの fqdn または Ip アドレス**] をクリックし、着信または発信の PSTN 通話をルーティングするために、存続可能 branch Appliance または存続可能ブランチサーバーが関連付けられているゲートウェイピアの fqdn または ip アドレスを入力します。
    
    <div>
    

    > [!IMPORTANT]  
    > 存続可能ブランチ アプライアンスを定義すると、このアプライアンスは、PSTN 接続で存続可能ブランチ アプライアンス内部の仲介サーバーが接続するゲートウェイとなります。

    
    </div>

8.  [**IP/PSTN ゲートウェイのリッスン ポート**] をクリックし、既定のポートに設定します。

9.  [ **Sip トランスポートプロトコル**] で、存続可能ブランチアプライアンスまたは存続可能ブランチサーバーが使用するトランスポートプロトコルをクリックし、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由により、トランスポート層セキュリティ (TLS) を使用することを強くお勧めします。 存続可能ブランチ アプライアンスを定義する場合は、存続可能ブランチ アプライアンスのベンダー ドキュメントを参照して、その存続可能ブランチ アプライアンスが TLS プロトコルをサポートすることを確認してください。

    
    </div>

10. コンソール ツリーで新しい存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを右クリックし、[**トポロジ**] をクリックしてから [**公開**] をクリックします。

**次のステップ**: [Lync Server 2013-ブランチサイトタスクを使用した存続可能ブランチアプライアンスまたはサーバーの展開](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

