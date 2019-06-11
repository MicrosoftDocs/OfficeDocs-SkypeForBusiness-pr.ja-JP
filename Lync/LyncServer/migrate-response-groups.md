---
title: 応答グループの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>応答グループの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-09-23_

ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイル、および、従来の展開から Lync Server 2013 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの通話は、Lync Server 2013 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールでは処理されなくなりました。

<div>


> [!NOTE]  
> すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、最初にすべてのユーザーを移動することをお勧めします。 特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。



</div>

応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。 応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。 **ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。

<div>


> [!NOTE]  
> 従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。



</div>

従来のプールから Lync Server 2013 に応答グループを移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。

<div>


> [!IMPORTANT]  
> 応答グループの移行コマンドレットは、プール全体の応答グループの構成を移動します。 移行する特定のグループ、キュー、またはワークフローを選ぶことはできません。



</div>

応答グループを移行した後、Lync Server コントロールパネルまたは Lync Server Management Shell コマンドレットを使用して、すべてのエージェントグループ、キュー、ワークフローが正常に移動されたことを確認する必要があります。

応答グループを移行しても、Lync Server 2010 応答グループは削除されません。 Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、移行後に応答グループを管理すると、Lync Server 2010 応答グループと Lync Server 2013 応答グループの両方を表示できます。 Lync Server 2013 応答グループにのみ更新プログラムを適用する必要があります。 Lync Server 2010 応答グループは、ロールバック目的でのみ保持されます。

<div>


> [!WARNING]  
> 移行が完了し、新しい応答グループが作成されると、Lync Server コントロールパネルと Lync server 管理シェルに、各返信グループの Lync Server 2010 および Lync Server 2013 のバージョンが表示されます。 Lync server コントロールパネルまたは Lync Server 管理シェルを使用して、Lync Server 2010 応答グループを削除しないでください。 いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。 Lync server 2010 プールの使用を停止すると、Lync Server 2010 応答グループは削除されます。



</div>

<div>


> [!IMPORTANT]  
> プールを廃止するまでは、前の展開からデータを削除しないことをお勧めします。 また、移行した後すぐに応答グループをエクスポートすることを強くお勧めします。 Lync Server 2010 応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、Lync Server 2013 応答グループを再起動することができます。



</div>

Lync Server 2013 では、**ワークフローの種類**と呼ばれる新しい返信グループ機能が導入されています。 **ワークフローの種類**は、**管理**または**非**管理を行うことができます。 すべての応答グループは、**ワークフローの種類**が [**非管理**] に設定され、[管理者] リストが空の状態で移行されます。

**移動-CsRgsConfiguration**コマンドレットを実行しても、ロールバックのために、エージェントグループ、キュー、ワークフロー、オーディオファイルは従来のプールに残ります。 ただし、従来のプールにロールバックする必要がある場合は、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを従来のプールに戻す必要があります。

回答グループの構成を移行するための次の手順では、従来のプールと Lync Server 2013 プールの間に1対1のリレーションシップがあることを前提としています。 移行および展開中にプールを統合または分割する場合は、どのレガシプールが Lync Server 2013 プールにマッピングされるかを計画する必要があります。

<div>

## <a name="to-migrate-response-group-configurations"></a>応答グループの構成を移行するには

1.  RTCUniversalServerAdmins グループのメンバーであるアカウントか、同等の管理者権限と権限を持つアカウントでコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    次に例を示します。
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  応答グループとエージェントを Lync Server 2013 プールに移行した後、サインインとサインアウトに使用するエージェントの URL は Lync Server 2013 URL であり、[**ツール**] メニューから使用できます。 ブックマークなどの参照を新しい URL に更新するようにエージェントに通知します。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して応答グループの移行を確認するには

1.  RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションウィンドウで、[**応答グループ**] をクリックします。

4.  [**ワークフロー** ] タブで、Lync Server 2010 環境内のすべてのワークフローが一覧に含まれていることを確認します。

5.  [**キュー** ] タブをクリックして、Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。

6.  [**グループ**] タブをクリックし、Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用して応答グループの移行を確認するには

1.  RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。
    
    次のコマンドレットの詳細については、次を実行します。
    
        Get-Help <cmdlet name> -Detailed

3.  次のコマンドレットを実行します。
    
        Get-CsRgsAgentGroup

4.  Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。

5.  次のコマンドレットを実行します。
    
        Get-CsRgsQueue

6.  Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。

7.  次のコマンドレットを実行します。
    
        Get-CsRgsWorkflow

8.  Lync Server 2010 環境内のすべてのワークフローが一覧に含まれていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

