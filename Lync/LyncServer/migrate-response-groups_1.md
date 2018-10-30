---
title: 応答グループを移行する
TOCTitle: 応答グループを移行する
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48272203
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 応答グループを移行する

 

_**トピックの最終更新日:** 2012-10-19_

ユーザーを Lync Server 2013 プールに移動した後、応答グループを移行できます。応答グループの移行には、エージェント グループ、キュー、ワークフロー、オーディオ ファイルのコピー、およびレガシ展開から Lync Server 2013 プールへの 応答グループ連絡先オブジェクトの移動が含まれます。レガシ応答グループを移行した後、応答グループへの通話は Lync Server 2013 プールの 応答グループ アプリケーションによって処理され、レガシ プールによっては処理されなくなります。

> [!NOTE]
> すべてのユーザーを Lync Server 2013 プールに移動する前に応答グループを移行することもできますが、まずすべてのユーザーを移動することをお勧めします。特に、応答グループ エージェントであるユーザーは、Lync Server 2013 プールに移動されるまでは新機能の一部を使用できません。


応答グループを移行する前に、応答グループ アプリケーションを含む Lync Server 2013 プールを展開しておく必要があります。エンタープライズ VoIP を展開すると、応答グループ アプリケーションが既定でインストールされ、アクティブ化されます。応答グループ アプリケーションがインストールされていることを確認するには、**Get-CsService–ApplicationServer** コマンドレットを実行します。

> [!NOTE]
> レガシ応答グループを移行する前に、Lync Server 2013 プールに新しい Lync Server 2013 応答グループを作成できます。


レガシ プールから Lync Server 2013 に応答グループを移行するには、**Move-CsRgsConfiguration** コマンドレットを実行します。**Move-CsRgsConfiguration** コマンドレットを実行する前に、まず Windows Management Instrumentation (WMI) 下位互換性インターフェイス パッケージをインストールする必要があります。このアプリケーションは、OCSWMIBC.msi を実行してインストールします。OCSWMIBC.msi は、インストール メディアの Setup フォルダーにあります。


> [!IMPORTANT]
> 応答グループ移行コマンドレットによって、プール全体の 応答グループ構成が移動されます。特定のグループ、キュー、またはワークフローを選択して移行することはできません。



応答グループを移行した後、公式エージェントが応答グループへのサインインおよびサインアウトに使用する URL を更新する必要があります。また、Lync Server コントロール パネルまたは Lync Server 管理シェル コマンドレットを使用して、すべてのエージェント グループ、キュー、およびワークフローが正常に移動されていることを確認する必要があります。


> [!TIP]
> 応答グループを移行しても、Office Communications Server 2007 R2 応答グループは削除されません。Office Communications Server 2007 R2 応答グループは削除しないでください。Office Communications Server 2007 R2 応答グループを削除すると、Lync Server 2013 の応答グループが機能しなくなります。




> [!IMPORTANT]
> プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。また、移行直後に応答グループをエクスポートすることを強くお勧めします。Office Communications Server 2007 R2 応答グループが削除された場合は、応答グループをバックアップから復元することで、Lync Server 2013 応答グループを再び実行できます。



**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。


> [!IMPORTANT]
> プールの使用を停止するまで、従来のプールから応答グループのデータを削除しないようにすることをお勧めします。



応答グループ構成の移行後の手順では、レガシ プールと Lync Server 2013 プールとの間に一対一の関係があることを前提としています。移行および展開中にプールを統合または分割する場合は、レガシ プールと Lync Server 2013 プールとの間のマッピング関係を計画する必要があります。

## 応答グループ構成を移行するには

1.  インストール メディアの Setup フォルダーで OCSWMIBC.msi を検索し、これをインストールします。

2.  RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。

3.  Lync Server 管理シェルを開きます。

4.  コマンドラインで、次のように入力します。
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    次に例を示します。
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Office Communications Server 2007 R2 環境に Microsoft Office Communicator 2007 R2 の \[応答グループ\] タブを展開していた場合は、そのタブを Office Communicator 2007 R2 tabs.xml ファイルから削除します。
    
    > [!NOTE]
    > 正規のエージェントが通話を受信するには、[応答グループ] タブを使用して応答グループにサインインする必要がありました。[応答グループ] タブを展開していた場合は、その展開時に、Office Communicator 2007 R2 tabs.xml ファイルの場所を選択しています。


6.  各エージェントが各応答グループにサインインおよびサインアウトするために必要な更新後の URL をユーザーに付与します。
    
    > [!NOTE]
    > この URL は、一般的には、https://webpoolFQDN/RgsClients/Tab.aspx です。&quot;webpoolFQDN&quot; は、前の手順で Lync Server 2013 に移行したプールに関連付けられる Web プールの完全修飾ドメイン名 (FQDN) です。
    
    > [!NOTE]
    > この手順は、ユーザーを Lync 2013 にアップグレードした後は不要です。この URL は、Lync の [<strong>ツール</strong>] メニューから使用できます。


## Lync Server コントロール パネルを使用して応答グループの移行を確認するには

1.  Lync Server コントロール パネルを開きます。

2.  左側のナビゲーション ウィンドウで \[**応答グループ**\] をクリックします。

3.  \[**ワークフロー**\] タブで、Office Communications Server 2007 R2 環境のすべてのワークフローがリストに含まれていることを確認します。

4.  \[**キュー**\] タブで、Office Communications Server 2007 R2 環境のすべてのキューがリストに含まれていることを確認します。

5.  \[**グループ**\] タブをクリックし、Office Communications Server 2007 R2 環境のすべてのエージェント グループがリストに含まれていることを確認します。

## コマンドレットを使用して応答グループの移行を確認するには

1.  Lync Server 管理シェルを開きます。
    
    各コマンドレットの詳細については、次のように実行してください。
    
        Get-Help <cmdlet name> -Detailed

2.  コマンドラインで、次のように入力します。
    
        Get-CsRgsAgentGroup

3.  Office Communications Server 2007 R2 環境のすべてのエージェント グループがリストに含まれていることを確認します。

4.  コマンドラインで、次のように入力します。
    
        Get-CsRgsQueue

5.  Office Communications Server 2007 R2 環境のすべてのキューがリストに含まれていることを確認します。

6.  コマンドラインで、次のように入力します。
    
        Get-CsRgsWorkflow

7.  Office Communications Server 2007 R2 環境のすべてのワークフローがリストに含まれていることを確認します。

