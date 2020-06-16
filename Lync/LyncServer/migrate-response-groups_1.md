---
title: 応答グループを移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>応答グループを移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行することができます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、およびオーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Lync Server 2013 プールに移動することが含まれます。 従来の応答グループを移行した後、応答グループへの通話は Lync Server 2013 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールによって処理されなくなりました。

<div>


> [!NOTE]  
> すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、すべてのユーザーを最初に移動することをお勧めします。 特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。



</div>

応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。 応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。 **ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。

<div>


> [!NOTE]  
> 従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。



</div>

応答グループを従来のプールから Lync Server 2013 に移行するには、**移動-CsRgsConfiguration**コマンドレットを実行します。 **Move-CsRgsConfiguration** コマンドレットを実行する前に、まず Windows Management Instrumentation (WMI) 下位互換性インターフェイス パッケージをインストールする必要があります。 このアプリケーションは、OCSWMIBC.msi を実行してインストールします。 OCSWMIBC.msi は、インストール メディアの Setup フォルダーにあります。

<div>


> [!IMPORTANT]  
> 応答グループ移行コマンドレットは、プール全体の応答グループの構成を移動します。 特定のグループ、キュー、またはワークフローを選択して移行することはできません。



</div>

応答グループを移行した後、正式エージェントが応答グループにサインインおよびサインアウトするために使用する URL を更新し、Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドレットを使用して、すべてのエージェントグループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。

<div>


> [!WARNING]  
> 応答グループを移行する場合、Office Communications Server 2007 R2 応答グループは削除されません。 Office Communications Server 2007 R2 応答グループは削除しないでください。 Office Communications Server 2007 R2 応答グループを削除すると、Lync Server 2013 の応答グループは動作を停止します。



</div>

<div>


> [!IMPORTANT]  
> プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。 また、移行直後に応答グループをエクスポートすることを強くお勧めします。 Office Communications Server 2007 R2 応答グループが削除された場合は、バックアップから応答グループを復元して、Lync Server 2013 応答グループを再度実行することができます。



</div>

**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。 ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。

<div>


> [!IMPORTANT]  
> プールの使用を停止するまで、従来のプールから応答グループのデータを削除しないようにすることをお勧めします。



</div>

応答グループの構成を移行する手順では、従来のプールと Lync Server 2013 プール間の1対1の関係があることを前提としています。 移行と展開時にプールを統合または分割する予定の場合は、どの従来のプールを Lync Server 2013 プールにマッピングするかを計画する必要があります。

<div>

## <a name="to-migrate-response-group-configurations"></a>応答グループの構成を移行するには

1.  インストール メディアの Setup フォルダーで OCSWMIBC.msi を検索し、これをインストールします。

2.  RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。

3.  Lync Server 管理シェルを開きます。

4.  コマンドラインで、次のように入力します。
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    次に例を示します。
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Office Communications Server 2007 R2 環境の Microsoft Office Communicator 2007 R2 用の [応答グループ] タブを展開した場合は、そのタブを Office Communicator 2007 R2 tabs.xml ファイルから削除します。
    
    <div>
    

    > [!NOTE]  
    > 正規のエージェントが通話を受信するには、[応答グループ] タブを使用して応答グループにサインインする必要がありました。 [応答グループ] タブを展開した場合は、展開時に Office Communicator 2007 R2 tabs.xml ファイルの場所を選択しています。

    
    </div>

6.  各エージェントが各応答グループにサインインおよびサインアウトするために必要な更新後の URL をユーザーに付与します。
    
    <div>
    

    > [!NOTE]  
    > 通常、URL は https://webpoolFQDN/RgsClients/Tab.aspx 、Lync Server 2013 に移行したばかりのプールに関連付けられている web プールの完全修飾ドメイン名 (fqdn) である webpoolFQDN です。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync の [<STRONG>ツール</STRONG>] メニューから URL を利用できるため、ユーザーが lync 2013 にアップグレードした後は、この手順は必要ありません。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して応答グループの移行を確認するには

1.  Lync Server コントロール パネルを開きます。

2.  左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。

3.  [**ワークフロー** ] タブで、Office Communications Server 2007 R2 環境のすべてのワークフローがリストに含まれていることを確認します。

4.  [**キュー** ] タブをクリックして、Office Communications Server 2007 R2 環境のすべてのキューがリストに含まれていることを確認します。

5.  [**グループ**] タブをクリックし、Office Communications Server 2007 R2 環境のすべてのエージェントグループがリストに含まれていることを確認します。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>コマンドレットを使用して応答グループの移行を確認するには

1.  Lync Server 管理シェルを開きます。
    
    各コマンドレットの詳細については、次のように実行してください。
    
        Get-Help <cmdlet name> -Detailed

2.  コマンド ラインで、次のように入力します。
    
        Get-CsRgsAgentGroup

3.  Office Communications Server 2007 R2 環境のすべてのエージェントグループがリストに含まれていることを確認します。

4.  コマンドラインで、次のように入力します。
    
        Get-CsRgsQueue

5.  Office Communications Server 2007 R2 環境のすべてのキューがリストに含まれていることを確認します。

6.  コマンドラインで、次のように入力します。
    
        Get-CsRgsWorkflow

7.  Office Communications Server 2007 R2 環境のすべてのワークフローがリストに含まれていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

