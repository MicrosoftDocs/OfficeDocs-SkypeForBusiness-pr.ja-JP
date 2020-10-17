---
title: 移行プロセス-詳細
description: 移行プロセス-詳細。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569583"
---
# <a name="migration-process---details"></a>移行プロセス-詳細

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーのどちらかを移行するには、次の前提条件と詳細な手順を使用します。

<div>

## <a name="prerequisites-for-migration"></a>移行の前提条件

Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーに移行する前に、以下の前提条件を満たしていることを確認してください。

1.  少なくとも1つの Lync Server 2013 プールを展開します。 複数の Lync Server 2013 プールがある場合は、どの Lync server 2013 プールを新しい Lync Server 2013 常設チャットサーバープールのホームプールにするかを決定します。

2.  Lync Server 2013、常設チャットサーバープールをインストールします。 空 (カテゴリ、ルーム、またはアドインはありません) になります。 従来のカテゴリ、ルーム、またはアドインを移行する前に、Lync Server 2013 の常設チャットサーバーの展開で、ルーム、カテゴリ、またはアドインを作成できます。
    
    <div>
    

    > [!IMPORTANT]  
    > 新しく作成されたアイテムが、移行する従来のアイテムと競合する可能性があることに注意してください。 名前付けの競合を回避します。そうしないと、従来のデータが移行されるときに上書きされます。

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>移行のためのソースデータの準備

移行のためにソースデータを適切に準備するには、次の手順を実行します。

1.  Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットのソースデータベースをバックアップします。 SQL Server のバックアップの詳細については、「」の「バックアップの概要 (SQL Server)」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=254851> 。
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory ドメインサービスは同じである必要があります。 移行の条件として、異なる展開 (特に、別の Active Directory フォレスト) 内のプールに移行することはできません。

    
    </div>

2.  Lync Server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャットチャットルームおよびカテゴリ構成を調べます。 既存のレガシ展開で、カテゴリ、ルーム、またはアドインに加えた変更は、グループチャット管理ツールによって行われます。
    
    <div>
    

    > [!TIP]  
    > Lync Server 2013 のカテゴリ、ルーム、またはアドインに変更が加えられた場合、常設チャットサーバーの展開は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットによって実行されます。

    
    </div>
    
    従来のシステムを移行用に準備するには、次の手順を実行します。
    
    1.  常設チャットサーバーは、カテゴリの深い階層のセットとは異なり、1つのレベルのカテゴリをサポートします。 移行後、サブカテゴリには完全な親カテゴリ名のプレフィックスが付けられます。 結果として得られる構造が要件を満たすように、既存のカテゴリ構造を単純化して統合する必要がある場合があります。
    
    2.  ルートカテゴリの **マネージャー** を確認します。 このレベルでマネージャーが存在する場合、これらのユーザーは移行後 **にすべてのルームに管理者** として追加されます。 組織の要件ではない場合は、これらのマネージャーをルートカテゴリから削除する必要があります。
    
    3.  ルーム名の長さを確認します。 移行後、カテゴリ構造が簡略化されているため、ルームが子カテゴリの下に存在する場合は、完全な親カテゴリ名のプレフィックスが付いています。 名前付けの制限は、親カテゴリ名を含む256文字です。 ルーム名の長さを確認し、長すぎる場合は、長さを短くする必要があります。
    
    4.  Lync Server 2013 で、カテゴリの **招待** の設定が true に設定されている場合は、そのカテゴリの下にあるルームへの招待に true または false を選択できます。 ただし、カテゴリの招待の設定が false に設定されている場合は、そのカテゴリの下のルームの招待がオフになります。 移行の前に、特定のカテゴリの下に会議室が存在するようにするには、従来の Lync Server グループチャットサーバーバージョンの招待の設定をリセットする必要があります。 それ以外の場合、移行時に Lync Server 2013 は警告を表示し、ルームを既定値の false に設定します。
    
    5.  チャットルームでファイルを使用した場合は、移行後に新しい常設チャットファイルストアに対してファイルを手動で XCOPY する必要があります。 このツールは、この操作を行いません。
    
    6.  フェデレーションユーザーとのフェデレーションユーザーおよびルームがある場合は、常設チャットサーバーがフェデレーションをサポートしていないことに注意してください。 フェデレーションユーザーがいるルームは移行されます。ただし、フェデレーションアクセスはサポートされていないため、ユーザー自体はコンテンツにアクセスできません。
    
    7.  移行しないルームを特定し、無効としてマークします。
    
    8.  チャットルームのコンテンツを移行する日付を指定します。 たとえば、2010年1月1日より前のメッセージは移行しないようにする必要がある場合があります。

</div>

<div>

## <a name="performing-the-migration"></a>移行の実行

従来のグループチャットサーバーを移行するには、次の手順を実行します。

1.  Lync Server 2010、グループチャット、Office Communications Server 2007 R2 グループチャット、または Lync Server 2013、常設チャットサーバーサービスをシャットダウンします。 すべてのサービスを停止する必要があるので、ダウンタイムが十分に発生した場合に限り、この操作を計画してください。 前述のように、現在のグループチャットデータベースをバックアップしてください。

2.  常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして、Windows PowerShell **export-cspersistentchatdata** コマンドレットを実行します。 エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。
    
    エクスポートされたコンテンツを検査します。

3.  インポートの準備ができたら、Lync Server 2013、常設チャットサーバーサービスをシャットダウンします。 すべてのサービスを停止する必要があるので、ダウンタイムが十分に発生した場合には、そのための計画を立てる必要があります。

4.  移行前に、Lync Server 2013 展開でカテゴリ、ルーム、またはアドインを作成した場合は、常設チャットデータベースのバックアップを実行します。 エクスポート/インポートプロセスでは、従来のデータを Lync Server 2013 の展開にマージできますが、コンテンツが誤って上書きされた場合 (たとえば、名前の競合がまだ存在している場合) は、データベースをバックアップする必要があります。

5.  Windows PowerShell Export-cspersistentchatdata コマンドレット (インポートツール) を実行し、 **WhatIf**コマンドを使用して、常設チャットサーバープールのバックエンドサーバーに移行**済み**データを設定します。 簡素化された管理モデルに対応するために、一部の変換がプロセスで行われます。 表示されるエラーまたは警告を修正します。

6.  常設チャットサーバーの Windows PowerShell **export-cspersistentchatdata** コマンドレットを常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして実行します。 エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。

7.  アップロードされたすべてのファイル (フォルダー全体) は、新しい Lync Server 2013、常設チャットファイルストアに対して XCOPY する必要があります。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (クライアント) は、チャットルームでのファイルのアップロードまたは表示をサポートしていません。 従来のクライアントを使用して、ルーム内のファイルを投稿および表示することはできます。

    
    </div>

8.  Lync server 2010、グループチャットまたは Office Communications Server 2007 R2 グループチャット参照サーバー URI を Lync Server 2013、常設チャットサーバーの連絡先オブジェクトに移植します。 Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットクライアントが、クライアント側の構成を変更せずに、移行後に最新の Lync 2013、常設チャット (クライアント) に接続する必要がある場合は、次の手順を実行する必要があります。
    
      - Ocschat@ \<domainName\> .Com 参照サーバーのユーザーアカウントを削除します。 これは、Lync Server 2010 のグループチャットの参照サービスを指すために使用されました。 後で、そのプールをアンインストールして、信頼できるエントリを削除することができます。
    
      - 従来のエンドポイント (常設チャットサーバーの連絡先オブジェクト) を作成するには、同じ SIP URI を使用して Windows PowerShell コマンドレット **new-cspersistentchatendpoint**を実行します。これにより、サービスの再起動時にレガシクライアントが効果的に動作するようになります。
    
    この時点で、必須の移行プロセスは完了しています。 Lync 2010 グループチャット (クライアント) または Office Communicator 2007 R2 グループチャット (クライアント) は、現在、透過的に新しい常設チャットサーバープールに接続できます。
    
    Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットの追加の使用停止手順に従います。

9.  新しい常設チャットサーバープール内のすべてのコンピューターをオンにして、常設チャットサーバーサービスを開始します。

10. Lync Server コントロールパネルおよび Windows PowerShell コマンドレットを使用して、データが正常に移行されたことを確認します。

11. グループチャットサーバープールのコンピューターから Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットをアンインストールします。

12. Windows PowerShell コマンドレットを使用して、信頼されたアプリケーションと信頼されたアプリケーションプールを削除します。 これにより、これらのアイテムは中央管理ストアと、関連付けられている信頼済みサービスエントリ (TSEs) から Active Directory から削除されます。 別の方法として、この手順はトポロジビルダーを使用しても機能します (信頼されたアプリケーション/プールにも専用のノードがあります)。

13. これで、新しいクライアントを使用して常設チャットサーバーの機能を有効にすることができるようになります。 常設チャットサーバーの有効化の詳細については、「 [Lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 は、複数の常設チャットサーバープールをサポートしています。 ただし、Lync 2010 グループチャットまたは Office Communications Server 2007 R2 &nbsp; グループチャットプールを1つの Lync server 2013、常設チャットサーバープールに移行することはサポートされています。 展開に新しい常設チャットサーバープールを追加して、規制要件を満たすようにすることができます (たとえば、特定の地域内のデータを保持する)。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

