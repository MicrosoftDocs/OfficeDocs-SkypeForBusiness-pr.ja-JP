---
title: 応答グループの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf7f0fa04f494eb49a0537011d5f9affcc68065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>応答グループの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

ユーザーが Lync Server 2013 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイルのコピー、および従来の展開から Lync Server 2013 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの通話は、Lync Server 2013 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールでは処理されなくなりました。

<div>


> [!NOTE]  
> すべてのユーザーを Lync Server 2013 プールに移動する前に、応答グループを移行することもできますが、最初にすべてのユーザーを移動することをお勧めします。 特に、応答グループのエージェントであるユーザーは、Lync Server 2013 プールに移動するまで、新機能のすべての機能を利用できません。



</div>

応答グループを移行する前に、応答グループアプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。 応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。 **ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。

<div>


> [!NOTE]  
> 従来の応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成することができます。



</div>

従来のプールから Lync Server 2013 に応答グループを移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。 **移動-CsRgsConfiguration**を実行する前に、まず Windows Management INSTRUMENTATION (WMI) 下位互換性インターフェイスパッケージをインストールする必要があります。 OCSWMIBC を実行して、このアプリケーションをインストールします。 インストールメディアの OCSWMIBC は、セットアップフォルダーで見つけることができます。

<div>


> [!IMPORTANT]  
> 応答グループの移行コマンドレットは、プール全体の応答グループの構成を移動します。 移行する特定のグループ、キュー、またはワークフローを選ぶことはできません。



</div>

応答グループを移行した後、正式なエージェントが応答グループにサインインまたはサインアウトするために使用する URL を更新して、Lync Server コントロールパネルまたは Lync Server Management Shell コマンドレットを使用して、すべてのエージェントグループ、キュー、ワークフローが移動されたことを確認する必要があります。できる.

<div>


> [!WARNING]  
> 応答グループを移行しても、Office Communications Server 2007 R2 応答グループは削除されません。 Office Communications Server 2007 R2 応答グループは削除しないでください。 Office Communications Server 2007 R2 応答グループを削除すると、Lync Server 2013 の返信グループが機能しなくなります。



</div>

<div>


> [!IMPORTANT]  
> プールを廃止するまでは、前の展開からデータを削除しないことをお勧めします。 また、移行した後すぐに応答グループをエクスポートすることを強くお勧めします。 Office Communications Server 2007 R2 応答グループが削除された場合は、バックアップから応答グループを復元して、Lync Server 2013 応答グループをもう一度実行することができます。



</div>

**移動-CsRgsConfiguration**コマンドレットを実行しても、ロールバックのために、エージェントグループ、キュー、ワークフロー、オーディオファイルは従来のプールに残ります。 ただし、従来のプールにロールバックする必要がある場合は、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを従来のプールに戻す必要があります。

<div>


> [!IMPORTANT]  
> プールを廃止するまで、従来のプールから応答グループのデータを削除しないことをお勧めします。



</div>

応答グループの構成を移行するための手順では、従来のプールと Lync Server 2013 プールの間に1対1の関係があることを前提としています。 移行および展開中にプールを統合または分割する場合は、どのレガシプールが Lync Server 2013 プールにマッピングされるかを計画する必要があります。

<div>

## <a name="to-migrate-response-group-configurations"></a>応答グループの構成を移行するには

1.  インストールメディアのセットアップフォルダーで OCSWMIBC を見つけてインストールします。

2.  RTCUniversalServerAdmins グループのメンバーであるアカウントか、同等の管理者権限と権限を持つアカウントでコンピューターにログオンします。

3.  Lync Server 管理シェルを開きます。

4.  コマンドラインで、次のように入力します。
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    次に例を示します。
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Office Communications Server 2007 R2 環境で Microsoft Office Communicator 2007 R2 の [返信グループ] タブを展開した場合は、Office Communicator 2007 R2 のタブからタブを削除します。
    
    <div>
    

    > [!NOTE]  
    > 正式なエージェントは、応答グループタブを使用して、通話を受ける前に応答グループにサインインします。 [応答グループ] タブを展開した場合は、Office Communicator 2007 R2 のタブの場所を選択します。

    
    </div>

6.  エージェントが応答グループにサインインまたはサインアウトするために必要となる、更新された URL をユーザーに提供します。
    
    <div>
    

    > [!NOTE]  
    > URL は通常https://webpoolFQDN/RgsClients/Tab.aspx、webpoolFQDN が Lync Server 2013 に移行したプールに関連付けられている web プールの完全修飾ドメイン名 (FQDN) です。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > ユーザーが Lync 2013 にアップグレードした後、この手順は必要ありません。 Lync の [<STRONG>ツール</STRONG>] メニューから URL を利用できます。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して応答グループの移行を確認するには

1.  Lync Server コントロールパネルを開きます。

2.  左側のナビゲーションウィンドウで、[**応答グループ**] をクリックします。

3.  [**ワークフロー** ] タブで、Office Communications Server 2007 R2 環境内のすべてのワークフローが一覧に含まれていることを確認します。

4.  [**キュー** ] タブをクリックし、Office Communications Server 2007 R2 環境内のすべてのキューがリストに含まれていることを確認します。

5.  [**グループ**] タブをクリックし、Office Communications Server 2007 R2 環境内のすべてのエージェントグループがリストに含まれていることを確認します。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>コマンドレットを使用して応答グループの移行を確認するには

1.  Lync Server 管理シェルを開きます。
    
    次のコマンドレットの詳細については、次を実行します。
    
        Get-Help <cmdlet name> -Detailed

2.  コマンドラインで、次のように入力します。
    
        Get-CsRgsAgentGroup

3.  Office Communications Server 2007 R2 環境内のすべてのエージェントグループがリストに含まれていることを確認します。

4.  コマンドラインで、次のように入力します。
    
        Get-CsRgsQueue

5.  Office Communications Server 2007 R2 環境内のすべてのキューがリストに含まれていることを確認します。

6.  コマンドラインで、次のように入力します。
    
        Get-CsRgsWorkflow

7.  Office Communications Server 2007 R2 環境内のすべてのワークフローが一覧に含まれていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

