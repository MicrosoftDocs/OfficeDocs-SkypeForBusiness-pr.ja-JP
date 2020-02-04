---
title: 移行のプロセス - 詳細
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>移行のプロセス - 詳細

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットを Lync Server 2013、常設チャットサーバーに移行するには、次の前提条件と詳細な手順を使用します。

<div>

## <a name="prerequisites-for-migration"></a>移行の前提条件

Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットを Lync Server 2013、常設チャットサーバーに移行する前に、次の前提条件を満たしていることを確認してください。

1.  Lync Server 2013 プールを少なくとも1つ展開します。 複数の Lync Server 2013 プールがある場合は、新しい Lync server 2013 常設チャットサーバープールのホームプールにする Lync Server 2013 プールを決定します。

2.  Lync Server 2013 の常設チャットサーバープールをインストールします。 空 (カテゴリ、ルーム、アドインは含まれません) になります。 従来のカテゴリ、会議室、またはアドインを移行する前に、Lync Server 2013 の常設チャットサーバーの展開で、会議室、カテゴリ、アドインを作成することができます。
    
    <div>
    

    > [!IMPORTANT]  
    > 新しく作成されたアイテムは、移行した従来のアイテムと競合することがあります。 名前の競合を回避します。そうしないと、従来のデータが移行されるときに上書きされます。

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>移行のためのソースデータの準備

移行のためにソースデータを適切に準備するには、次の手順を実行します。

1.  Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットのソースデータベースをバックアップします。 SQL Server のバックアップの詳細については、「バックアップの概要 (SQL Server <http://go.microsoft.com/fwlink/p/?linkid=254851>)」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory ドメインサービスは同じである必要があります。 移行の条件として、別の展開 (具体的には別の Active Directory フォレスト) のプールに移行することはできません。

    
    </div>

2.  Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットルームとカテゴリ構成を検査します。 既存のレガシー展開で、カテゴリ、ルーム、またはアドインに対する変更は、グループチャット管理ツールによって実行されます。
    
    <div>
    

    > [!TIP]  
    > Lync Server 2013 の [カテゴリ]、[ルーム]、または [アドイン] に対する変更は、[Lync Server] コントロールパネルまたは Windows PowerShell コマンドレットによって実行されます。

    
    </div>
    
    次の手順に従って、移行用のレガシシステムを準備します。
    
    1.  常設チャットサーバーは、カテゴリの深い階層セットとは異なり、1つのレベルのカテゴリをサポートします。 移行後、サブカテゴリには完全な親カテゴリ名のプレフィックスが付きます。 結果としての構造が要件を満たすように、既存のカテゴリ構造を単純化してフラット化することをお勧めします。
    
    2.  ルートカテゴリの**マネージャー**を確認します。 このレベルにマネージャーが存在する場合、これらのユーザーは、移行後**にすべてのルームにマネージャー**として追加されます。 組織の要件ではない場合は、これらのマネージャーをルートカテゴリから削除する必要があります。
    
    3.  ルーム名の長さを確認します。 カテゴリ構造が簡素化されたため、移行後、カテゴリ構造が子カテゴリの下に存在する場合、そのルームには完全な親カテゴリ名のプレフィックスが付きます。 名前付けの制限は、親カテゴリ名を含む256文字です。 会議室名の長さを確認し、長すぎる場合は長さを短くする必要があります。
    
    4.  Lync Server 2013 で、カテゴリの**招待**の設定が true に設定されている場合は、そのカテゴリの下の会議室への招待について true または false を選ぶことができます。 ただし、カテゴリの招待状の設定が false に設定されている場合、そのカテゴリの下の [会議出席依頼] はオフになっています。 移行する前に、特定のカテゴリの下に会議室が存在するようにするには、従来の Lync Server グループチャットサーバーバージョンで招待の設定をリセットする必要があります。 そうしないと、移行中に、Lync Server 2013 で警告が表示され、会議室が false の既定値に設定されます。
    
    5.  チャットルームでファイルを使用した場合は、移行後にファイルを新しい常設チャットファイルストアに手動で XCOPY する必要があります。 この操作は、ツールでは実行できません。
    
    6.  フェデレーションされたユーザーとのフェデレーションユーザーとルームがある場合は、常設チャットサーバーでフェデレーションがサポートされていないことに注意してください。 フェデレーションされたユーザーがいるルームは移行されます。ただし、フェデレーションアクセスはサポートされていないため、ユーザー自身がコンテンツにアクセスすることはできません。
    
    7.  移行しない会議室を特定して、無効としてマークします。
    
    8.  チャットルームのコンテンツを移行する日付以降の日付を指定します。 たとえば、2010年1月1日より前にメッセージを移行したくない場合もあります。これらのメッセージは、移行に関連していない可能性があるためです。

</div>

<div>

## <a name="performing-the-migration"></a>移行の実行

次の手順を実行して、従来のグループチャットサーバーを移行します。

1.  Lync Server 2010、グループチャット、Office Communications Server 2007 R2 グループチャット、または Lync Server 2013、常設 Chat Server サービスをシャットダウンします。 すべてのサービスを停止する必要があるため、十分なダウンタイムがある場合は一度にこの操作を計画してください。 前に説明したように、現在のグループチャットデータベースをバックアップしてください。

2.  常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして Windows PowerShell **CsPersistentChatData**コマンドレットを実行します。 エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。
    
    エクスポートされた内容を検査します。

3.  インポートする準備ができたら、Lync Server 2013 の常設チャットサーバーサービスを終了します。 すべてのサービスを停止する必要があるため、十分なダウンタイムがある場合は一度にこの操作を計画してください。

4.  移行前に、Lync Server 2013 展開でカテゴリ、ルーム、またはアドインを作成した場合は、常設チャットデータベースのバックアップを実行します。 エクスポート/インポートプロセスでは、従来のデータを Lync Server 2013 の展開に統合することはできますが、コンテンツが誤って上書きされる場合 (たとえば、名前の競合が存在する場合)、データベースのバックアップを作成することをお勧めします。

5.  **WhatIf**コマンドを使用して Windows PowerShell **CsPersistentChatData**コマンドレット (インポートツール) を実行し、移行されたデータを使用して常設チャットサーバープールのバックエンドサーバーを設定します。 単純化された管理モデルに対応するために、一部の変換がプロセスで行われます。 表示されるエラーや警告を修正します。

6.  常設チャットサーバー Windows PowerShell の**CsPersistentChatData**コマンドレットを、常設チャット管理者の RBAC 役割 (CsPersistentChatAdministrator) のメンバーとして実行します。 エクスポート/インポートコマンドレットの詳細については、「 [Lync server 2013 で Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)」を参照してください。

7.  アップロードされたすべてのファイル (フォルダー全体) を新しい Lync Server 2013 の常設チャットファイルストアに XCOPY する必要があります。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (クライアント) では、チャットルームでのファイルのアップロードまたは表示はサポートされていません。 引き続き、従来のクライアントを使用して、会議室でのファイルの投稿と表示を行うことができます。

    
    </div>

8.  Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャット検索サーバー URI を Lync Server 2013、常設チャットサーバーの連絡先オブジェクトに移植します。 次の手順が必要なのは、Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットクライアントで、移行後に最新の Lync 2013、常設チャット (クライアント) に接続する必要がある場合に、クライアント側の構成が変更されない場合です。
    
      - Ocschat@\<domainName\>. .com 参照サーバーのユーザーアカウントを削除します。 これは、Lync Server 2010 の [グループチャット] で参照サービスを指すために使用されました。 プールをアンインストールして、後で信頼済みエントリを削除することができます。
    
      - 従来のエンドポイント (常設チャットサーバーの連絡先オブジェクト) を作成するには、同じ SIP URI を使用して Windows PowerShell コマンドレット**CsPersistentChatEndpoint を実行**します。これにより、サービスの再開時にレガシクライアントが効率的に動作するようになります。
    
    この時点では、必須の移行プロセスが完了しています。 Lync 2010 グループチャット (クライアント) または Office Communicator 2007 R2 グループチャット (クライアント) は、新しい常設チャットサーバープールに、透過的に接続できるようになりました。
    
    Lync Server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットのその他の廃止手順に従います。

9.  新しい常設チャットサーバープールのすべてのコンピューターをオンにして、常設チャットサーバーサービスを開始します。

10. Lync Server コントロールパネルと Windows PowerShell コマンドレットを使用して、データが正常に移行されたことを確認します。

11. グループチャットサーバープールのコンピューターから Lync 2010 グループチャットまたは Office Communicator 2007 R2 グループチャットをアンインストールします。

12. Windows PowerShell コマンドレットを使用して、信頼されているアプリケーションと信頼されているアプリケーションプールを削除します。 これにより、これらのアイテムは、サーバーの全体管理ストアと、関連付けられた信頼済みサービスエントリ (TSEs) から Active Directory から削除されます。 または、この手順はトポロジービルダーを使用して動作します (信頼されているアプリケーション/プールにも、専用のノードが含まれています)。

13. これで、新しいクライアントで常設チャットサーバー機能を有効にすることができます。 常設チャットサーバーを有効にする方法について詳しくは、「 [Lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)」をご覧ください。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 は、複数の常設チャットサーバープールをサポートしています。 ただし、Lync 2010 グループチャットまたは Office Communications Server 2007 R2&nbsp;グループチャットプールを単一の Lync Server 2013、常設チャットサーバープールに移行することをサポートしています。 新しい常設チャットサーバープールを展開に追加して、規制要件を満たすことができます (たとえば、特定の地理内のデータを保持する)。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

