---
title: 'Lync Server 2013: 付録 B: 存続可能ブランチ アプライアンスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>付録 B: Lync Server 2013 での存続可能ブランチ アプライアンスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

このトピックでは、Survivable Branch アプライアンスを管理する手順について説明します。 具体的には、Survivable Branch アプライアンスの置き換えと名前の変更方法と、Survivable Branch Appliance が関連付けられている Lync Server 2013 フロントエンドプールの変更方法について説明します。

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Survivable Branch アプライアンスを交換するには

1.  Survivable Branch アプライアンスで、すべての Lync Server 2013 サービスを停止します。 (Survivable Branch Appliance ベンダーのマニュアルをご覧ください。)

2.  勧めSurvivable Branch アプライアンスをドメインから削除します。

3.  次の手順に従って、Active Directory ドメインサービス内の Survivable Branch アプライアンスコンピューターオブジェクトを削除します。
    
      - Enterprise Admins グループのメンバーとしてメンバーサーバーにログオンします。
    
      - [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。
    
      - Survivable Branch Appliance オブジェクトを右クリックし、[**削除**] をクリックします。

4.  Survivable Branch Appliance コンピューターオブジェクトをもう一度追加します。 (「 [Lync Server 2013 の Active Directory に Survivable Branch Appliance を追加する」を](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)参照してください。)

5.  Active Directory の複製が行われるまで待ちます。

6.  Lync Server 管理シェルを開き、「 **Enable-CSTopology**機能」と入力します。

7.  新しい Survivable Branch Appliance をネットワークに接続し、「 [Survivable Branch appliance またはサーバーを Lync server 2013 に展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)する」の手順に従ってください。また、 [lync Server 2013 で Survivable 支店のアプライアンスまたはサーバーを展開してください。ブランチサイトタスク](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Survivable Branch アプライアンスの名前を変更するには

1.  ユーザーをセントラルサイトに移動します。 詳細については、「[ユーザーを Lync Server 2013 の別のプールに移動する](lync-server-2013-move-users-to-another-pool.md)」を参照してください。

2.  Survivable Branch アプライアンスで、すべての Lync Server 2013 サービスを停止します。 (Survivable Branch Appliance ベンダーのマニュアルをご覧ください。)

3.  次の手順に従って、トポロジから Survivable Branch アプライアンスを削除します。
    
      - [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server**]、[ **lync server Topology Builder**] の順にクリックします。
    
      - コンソールツリーで、[**ブランチサイト**] を展開し、Survivable ブランチアプライアンスをクリックして、操作ウィンドウで [**削除**] をクリックします。

4.  Survivable Branch アプライアンスをドメインから削除します。

5.  次の手順に従って、Active Directory 内の Survivable Branch Appliance コンピューターオブジェクトを削除します。
    
      - Enterprise Admins グループのメンバーとしてドメインコントローラーにログオンします。
    
      - [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。
    
      - Survivable Branch Appliance オブジェクトを右クリックし、[**削除**] をクリックします。

6.  Survivable Branch アプライアンスを工場出荷時のデフォルトに復元します。 (Survivable Branch Appliance ベンダーのマニュアルをご覧ください。)

7.  「 [Lync server 2013-セントラルサイトタスクを使用して Survivable Branch appliance またはサーバーを展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)する」の手順に従って、「 [lync server 2013 を使用して Survivable branch Appliance またはサーバーを展開する](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)」を参照してください。

8.  名前を変更した Survivable Branch アプライアンスにユーザーを移動します。 詳細については、「[ユーザーを Lync Server 2013 の別のプールに移動する](lync-server-2013-move-users-to-another-pool.md)」を参照してください。

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Survivable Branch アプライアンスが関連付けられている Lync Server フロントエンドプールを変更するには

1.  Survivable Branch アプライアンスから中央サイトの Lync Server フロントエンドプールにユーザーを移動します。 詳細については、「[ユーザーを Lync Server 2013 の別のプールに移動する](lync-server-2013-move-users-to-another-pool.md)」を参照してください。

2.  Survivable Branch アプライアンスで、すべての Lync Server サービスを停止します。 (Survivable Branch Appliance ベンダーのマニュアルをご覧ください)。

3.  次の手順に従って、Survivable Branch アプライアンスが関連付けられている Lync Server フロントエンドプールを更新します。
    
      - [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server**]、[ **lync server Topology Builder**] の順にクリックします。
    
      - [**ブランチサイト**の展開] を選びます。
    
      - 変更する Survivable Branch Appliance オブジェクトを右クリックして、[**プロパティの編集**] をクリックします。
    
      - [復元性] で、Survivable Branch アプライアンスが関連付けられる新しいフロントエンドプールを選択し、[**次へ**] をクリックします。
    
      - コンソールツリーで、新しい Survivable Branch アプライアンスを右クリックし、[ **Topology**] をクリックして、[**発行**] をクリックします。

4.  Survivable Branch アプライアンスで、すべての Lync Server サービスを再起動します。

5.  Survivable Branch アプライアンスをテストしてください。 詳細について[は、「Lync Server 2013 での Survivable Branch Appliance または Server のホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)」を参照してください。

6.  セントラルサイトの Lync Server フロントエンドプールのユーザーを Survivable Branch Appliance に移動します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

