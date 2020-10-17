---
title: 'Lync Server 2013: 付録 B: 存続可能ブランチアプライアンスの管理'
description: 'Lync Server 2013: 付録 B: 存続可能 Branch Appliance の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e66d97f538ee751d7bf12b0d0f70ff3a3f5576b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561833"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>付録 B: Lync Server 2013 での存続可能ブランチアプライアンスの管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

このトピックでは、存続可能ブランチアプライアンスを管理する手順について説明します。 具体的には、存続可能ブランチアプライアンスの置換と名前変更、および存続可能 Branch Appliance が関連付けられている Lync Server 2013 フロントエンドプールの変更方法について説明します。

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスを置き換えるには

1.  存続可能ブランチアプライアンス上のすべての Lync Server 2013 サービスを停止します。 (存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。

2.  勧めドメインから存続可能 Branch アプライアンスを削除します。

3.  Active Directory ドメインサービスの存続可能 Branch Appliance コンピューターオブジェクトを削除します。そのためには、次の手順を実行します。
    
      - Enterprise Admins グループのメンバーとしてメンバー サーバーにログオンします。
    
      - [**スタート**]、[**管理ツール**]、[**Active Directory ユーザーとコンピューター**] の順にクリックします。
    
      - 存続可能 Branch Appliance オブジェクトを右クリックし、[ **削除**] をクリックします。

4.  存続可能 Branch Appliance コンピューターオブジェクトをもう一度追加します。 (「 [Lync Server 2013 で存続可能 Branch Appliance を Active Directory に追加する」を](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)参照してください)。

5.  Active Directory のレプリケーションが行われるのを待ちます。

6.  [Lync Server 管理シェル] を開き、「 **Enable-CSTopology**方法」と入力します。

7.  新しい存続可能 Branch Appliance をネットワークに接続し、「 [存続可能 Branch appliance Or server With Lync server 2013-central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 」および「 [Deploy The 存続可能 Branch appliance Or Server with lync server 2013-Branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)」の手順を実行します。

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスの名前を変更するには

1.  ユーザーをセントラル サイトに移動します。 詳細については、「 [Move users to a Lync Server 2013」](lync-server-2013-move-users-to-another-pool.md)を参照してください。

2.  存続可能ブランチアプライアンス上のすべての Lync Server 2013 サービスを停止します。 (存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。

3.  トポロジから存続可能 Branch アプライアンスを削除するには、次の手順を実行します。
    
      - [**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
      - コンソールツリーで、[ **ブランチサイト**] を展開し、存続可能ブランチアプライアンスをクリックして、操作ウィンドウで [ **削除** ] をクリックします。

4.  ドメインから存続可能 Branch アプライアンスを削除します。

5.  Active Directory 内の存続可能 Branch Appliance コンピューターオブジェクトを削除するには、次の手順を実行します。
    
      - Enterprise Admins グループのメンバーとしてドメイン コントローラーにログオンします。
    
      - [**スタート**]、[**管理ツール**]、[**Active Directory ユーザーとコンピューター**] の順にクリックします。
    
      - 存続可能 Branch Appliance オブジェクトを右クリックし、[ **削除**] をクリックします。

6.  存続可能ブランチアプライアンスを出荷時の既定値に復元します。 (存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。

7.  「 [Lync server 2013-中央サイトタスクを使用した存続可能ブランチアプライアンスまたはサーバーの展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 」の手順に従って、「 [lync server 2013-branch site task」を使用して存続可能 branch Appliance または server を展開](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)します。

8.  名前を変更した存続可能 Branch Appliance にユーザーを移動します。 詳細については、「 [Move users to a Lync Server 2013」](lync-server-2013-move-users-to-another-pool.md)を参照してください。

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>存続可能ブランチ アプライアンスが関連付けられている Lync Server のフロントエンド プールを変更するには

1.  存続可能ブランチアプライアンスから中央サイトの Lync Server フロントエンドプールにユーザーを移動します。 詳細については、「 [Move users to a Lync Server 2013」](lync-server-2013-move-users-to-another-pool.md)を参照してください。

2.  存続可能ブランチアプライアンス上のすべての Lync Server サービスを停止します。 (存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。

3.  存続可能 Branch Appliance が関連付けられている Lync Server フロントエンドプールを更新するには、次の手順を実行します。
    
      - [**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。
    
      - [**ブランチ サイト**] を展開します。
    
      - 変更する存続可能 Branch Appliance オブジェクトを右クリックし、[**プロパティの編集**] をクリックします。
    
      - [復元] で、存続可能ブランチアプライアンスが関連付けられる新しいフロントエンドプールを選択し、[ **次へ**] をクリックします。
    
      - コンソールツリーで、新しい存続可能ブランチアプライアンスを右クリックし、[ **トポロジ**] をクリックして、[ **公開**] をクリックします。

4.  存続可能ブランチアプライアンス上のすべての Lync Server サービスを再起動します。

5.  存続可能ブランチアプライアンスをテストします。 詳細については、「 [存続可能ブランチアプライアンスまたはサーバー上の Lync server 2013 のホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)」を参照してください。

6.  中央サイトの Lync Server フロントエンドプールから存続可能ブランチアプライアンスにユーザーを移動します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

