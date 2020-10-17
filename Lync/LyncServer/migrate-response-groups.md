---
title: 応答グループを移行する
description: 応答グループを移行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570323"
---
# <a name="migrate-response-groups"></a>応答グループを移行する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-23_

ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行することができます。 応答グループの移行では、エージェントグループ、キュー、ワークフロー、オーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Lync Server 2013 プールに移動することが含まれます。 従来の応答グループを移行した後、応答グループへの通話は Lync Server 2013 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールによって処理されなくなりました。

<div>


> [!NOTE]  
> すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、すべてのユーザーを最初に移動することをお勧めします。 特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。



</div>

応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。 応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。 **ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。

<div>


> [!NOTE]  
> 従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。



</div>

応答グループを従来のプールから Lync Server 2013 に移行するには、 **移動-CsRgsConfiguration** コマンドレットを実行します。

<div>


> [!IMPORTANT]  
> 応答グループ移行コマンドレットは、プール全体の応答グループの構成を移動します。 特定のグループ、キュー、またはワークフローを選択して移行することはできません。



</div>

応答グループを移行した後、Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドレットを使用して、すべてのエージェントグループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。

応答グループを移行する場合、Lync Server 2010 応答グループは削除されません。 Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用して移行後に応答グループを管理すると、Lync Server 2010 応答グループと Lync Server 2013 応答グループの両方を表示することができます。 更新プログラムは、Lync Server 2013 応答グループにのみ適用する必要があります。 Lync Server 2010 応答グループは、ロールバックの目的でのみ保持されます。

<div>


> [!WARNING]  
> 移行が完了し、新しい応答グループが作成された後、lync server コントロールパネルおよび Lync server 管理シェルには、各応答グループの Lync Server 2010 および Lync Server 2013 のバージョンが表示されます。 Lync server コントロールパネルまたは Lync Server 管理シェルを使用して Lync Server 2010 応答グループを削除しないでください。 いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。 Lync server 2010 プールを使用停止にすると、Lync Server 2010 応答グループが削除されます。



</div>

<div>


> [!IMPORTANT]  
> プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。 また、移行直後に応答グループをエクスポートすることを強くお勧めします。 Lync Server 2010 応答グループを削除する必要がある場合は、バックアップから応答グループを復元して Lync Server 2013 応答グループを再度実行することができます。



</div>

Lync Server 2013 には、 **ワークフローの種類**と呼ばれる新しい応答グループ機能が導入されています。 [**ワークフローの種類**] は、[**管理**] または [**管理されていない**] に設定できます。 すべての応答グループは、[**ワークフローの種類**] が [**管理されていない**] に設定され、マネージャーの一覧が空の状態で移行されます。

**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。 ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。

応答グループ構成を移行するための次の手順では、従来のプールと Lync Server 2013 プール間の1対1の関係があることを前提としています。 移行と展開時にプールを統合または分割する予定の場合は、どの従来のプールを Lync Server 2013 プールにマッピングするかを計画する必要があります。

<div>

## <a name="to-migrate-response-group-configurations"></a>応答グループの構成を移行するには

1.  RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    次に例を示します。
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  応答グループとエージェントを Lync Server 2013 プールに移行すると、エージェントがサインインおよびサインアウトする際に使用する URL が Lync Server 2013 の URL になり、[ **ツール** ] メニューから利用できるようになります。 ブックマークなどの参照を、新しい URL に更新するようにエージェントに知らせてください。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server コントロール パネルを使用して応答グループの移行を確認するには

1.  RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。

4.  [ **ワークフロー** ] タブで、Lync Server 2010 環境内のすべてのワークフローがリストに含まれていることを確認します。

5.  [ **キュー** ] タブをクリックして、Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。

6.  [ **グループ** ] タブをクリックし、Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用して応答グループの移行を確認するには

1.  RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。
    
    各コマンドレットの詳細については、次のように実行してください。
    
        Get-Help <cmdlet name> -Detailed

3.  実行
    
        Get-CsRgsAgentGroup

4.  Lync Server 2010 環境内のすべてのエージェントグループがリストに含まれていることを確認します。

5.  実行
    
        Get-CsRgsQueue

6.  Lync Server 2010 環境内のすべてのキューがリストに含まれていることを確認します。

7.  実行
    
        Get-CsRgsWorkflow

8.  Lync Server 2010 環境内のすべてのワークフローがリストに含まれていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

