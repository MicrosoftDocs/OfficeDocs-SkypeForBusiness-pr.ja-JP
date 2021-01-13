---
title: Skype for Business Server でのアーカイブの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: '概要: このトピックでは、Skype for Business Server でのアーカイブを計画する方法について説明します。'
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810147"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Skype for Business Server でのアーカイブの計画
 
**概要:** このトピックでは、Skype for Business Server でのアーカイブを計画する方法について説明します。
  
企業やその他の組織には、特定の種類の通信内容を保持するように求める規制が業界や政府機関から多数課せられています。 組織にこのような要件がある場合は、Skype for Business Server のアーカイブを使用して、インスタント メッセージング (IM) および会議 (会議) 通信をアーカイブし、コンプライアンス要件の一部をサポートできます。
  
## <a name="archiving-components"></a>アーカイブ コンポーネント

Skype for Business Server は、次のアーカイブ コンポーネントを使用します。
  
- **アーカイブ エージェント:** 統合データ収集エージェントとも呼ばれます。 アーカイブ エージェント (統合データ収集エージェントとも呼ばれる) は、すべての Enterprise Edition フロントエンド プールと Standard Edition サーバーに自動的にインストールされ、アクティブ化されます。 アーカイブ エージェントは自動的にアクティブ化されます。ただし、アーカイブが有効になり、適切に構成されるまでは、実際にはメッセージは取得されません。 既定では、アーカイブは無効になっています。
    
- **アーカイブ データ ストレージ**。 Skype for Business Server のデータ ストレージは、Skype for Business Server SQL Server データベースとして実装するか、Exchange を展開している場合は Exchange ストレージと統合することができます。 
    
アーカイブにはファイルストレージも必要ですが、アーカイブではフロントエンド サーバーまたは Standard Edition サーバーと同じファイル ストレージが使用されます。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>アーカイブに関する組織の要件を決定する

アーカイブを実装するには、以下を決定して、アーカイブに関する組織の要件を満たす方法を決定する必要があります。
  
- **どのストレージ オプションを使用する必要があります**。 ストレージは、次の 2 つの方法の 1 つで実装するか、または両方の組み合わせを使用できます。
    
  - **Exchange ストレージ。** Exchange 展開を使用している場合は、Skype for Business Server と Exchange のアーカイブを統合して、Skype for Business Server と Exchange のアーカイブされたデータを Exchange に一緒に保存できます。 Microsoft Exchange 統合オプションを有効にした場合、Exchange Server にホームのユーザー メールボックスはアーカイブされたデータに Exchange ストレージを使用しますが、メールボックスが In-Place Hold に設定されている場合のみです。 既定では、Microsoft Exchange 統合は有効になっていません。
    
  - **Skype for Business Server ストレージ。** Exchange にホームではないユーザー、またはメールボックスを In-Place 保留にしていないユーザーがある場合、または展開内の一部またはすべてのユーザーに Microsoft Exchange 統合を使用しない場合は、SQL Server を使用して Skype for Business Server Archiving データベースを展開できます。
    
- **アーカイブを展開する場合**。 アーカイブは、Skype for Business Server の初期展開の一部として展開するか、既存の展開に追加できます。 Skype for Business Server アーカイブ ストレージ (SQL Server データベース) を使用するには、トポロジ ビルダーを使用してデータベースをトポロジに追加し、トポロジを再度公開します。 すべてのユーザーが Exchange にホームを置き、メールボックスを In-Place ホールドに設定している場合は、トポロジを更新する必要はないが、Microsoft Exchange 統合を有効にしてアーカイブされたデータを Exchange に保存する必要があるだけである。 
    
- **アーカイブが必要な組織内のサイトとユーザー**。 アーカイブ設定は、組織全体に対して構成できます。また、必要に応じて、特定のサイト、プール、ユーザー、およびユーザー グループに対して構成できます。
    
- **どのようなコンテンツをアーカイブする必要があります**。 アーカイブをグローバル レベルで指定するか、特定のサイトおよびユーザーに対して指定するかに関して、これらの各レベルで次の種類のコンテンツを有効にするかどうかを指定します。 
    
  - ピアツーピアのインスタント メッセージ
    
  - マルチパーティのインスタント メッセージである会議 (ミーティング)
    
  - アップロードされたコンテンツ (配付資料など) およびイベント関連のコンテンツ (参加、退席、アップロード、共有、表示設定の変更など) を含む会議コンテンツ
    
  - 会議中に共有するホワイトボードおよび投票
    
- **アーカイブできないコンテンツ**。 次の種類のコンテンツはアーカイブできません。 
    
  - ピアツーピア ファイル転送
    
  - ピアツーピアのインスタント メッセージおよび会議の音声ビデオ
    
  - ピアツーピアのインスタント メッセージおよび会議のデスクトップ/アプリケーション共有
    
    Skype for Business Server では、常設チャットの会話もアーカイブされません。 常設チャットの会話をアーカイブするには、常設チャット サーバーで展開できるコンポーネントであるコンプライアンス サービスを有効にして構成する必要があります。 詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015」を参照](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)してください。

    > [!NOTE] 
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
    
- **アーカイブされた資料を保持する期間**。 アーカイブ データベースは長期保持を目的としていないので、Skype for Business Server はアーカイブされたデータの電子検出 (検索) ソリューションを提供していないので、データを他のストレージに移動する必要があります。 Skype for Business Server は、アーカイブされたデータのエクスポートに使用できるセッション エクスポート ツールを提供し、アーカイブされたデータの検索可能なトランスクリプトを作成します。 
    
     グローバル ポリシー、および作成するサイトおよびユーザー ポリシーごとに、アーカイブおよびエクスポートされたデータを削除する場合を指定できます。 データの削除の詳細については、「Skype for Business Server でアーカイブされたデータの削除を管理する [」を参照してください](../../manage/archiving/purging-of-archived-data.md)。 セッション エクスポート ツールの使用の詳細については、「Skype for Business Server でアーカイブされたデータを [エクスポートする」を参照してください](../../manage/archiving/export-archived-data.md)。
    
- **内部通信または外部通信をアーカイブするかどうか。** 内部通信 (つまり、内部ユーザー間の通信)、外部通信 (少なくとも 1 人の内部ネットワーク外のユーザーが含まれる通信)、または両方のアーカイブを有効にできます。これらのオプションは、組織全体に対して指定することも、特定のサイトおよびプールに対して指定することもできます。既定では、どちらのオプションも無効です。
    
    > [!NOTE]
    > 内部通信または外部通信のアーカイブの制御は、Skype for Business ポリシーでのみ使用できます。 Exchange 統合アーカイブの場合、内部通信と外部通信の両方がアーカイブまたはアーカイブされません。 
  
- **重要モードを実装するかどうかを指定します**。 組織にアーカイブが必要な場合、重要モードを構成すると、Skype for Business Server でアーカイブを妨げる障害が発生した場合に IM および会議セッションがブロックされます。 例: 
    
  - Skype for Business Server ストレージ サービスに関する問題。 この場合、アーカイブが有効になっているユーザーに対して IM がブロックされます。
    
  - 使用できないファイル共有、またはストレージ サービスの問題。 この場合、障害発生時にプールにホストされているすべてのアクティブな会議が制限モードに切り替えられ、新しい会議をアクティブ化できません。
    
    障害から回復した後、IM および会議は自動的に回復します。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>アーカイブ展開と構成オプションの選択

サーバーを展開すると、アーカイブは各フロントエンド サーバーに自動的にインストールされますが、アーカイブは構成するまで有効になりません。 アーカイブの構成方法は、アーカイブの展開方法によって決まります。 アーカイブは、次のいずれかの方法で展開できます。
  
- Microsoft Exchange ストレージを使用する
    
- Skype for Business Server ストレージの使用
    
> [!NOTE]
> 両方の Skype for Business Server アーカイブ データベースを実装し、Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは Skype for Business Server アーカイブ ポリシーより優先されますが、メールボックスが In-Place 保持に設定されている Exchange にホームを持つユーザーにのみ適用されます。 Skype for Business のアーカイブは、Microsoft Exchange In-Place保持ポリシーに依存します。 
  
1 つのフロントエンド プールまたは Standard Edition サーバーのアーカイブを展開する場合は、展開内の他のすべてのフロントエンド プールと Standard Edition サーバーに対してアーカイブを有効にする必要があります。 会話または会議がホストされているプールでアーカイブが有効になっていない場合、すべての会議データがアーカイブされない可能性があります。 IM メッセージのアーカイブは引き続き機能しますが、会議のコンテンツとイベントはアーカイブされない場合があります。
  
> [!NOTE]
> 組織のセキュリティ標準を維持しながら管理タスクの委任を有効にするには、Skype for Business Server は役割ベースのアクセス制御 (RBAC) を使用します。 RBAC を使用すると、定義済みの管理者の役割にユーザーを割り当てることにより、管理者特権が付与されます。 Skype for Business のアーカイブ ポリシーと構成を構成するには、ユーザーを CsArchivingAdministrator の役割に割り当てる必要があります (別のコンピューターからリモートで行うのではなく、アーカイブが展開されているサーバーで直接構成が行われる場合を含む)。 アーカイブ展開に必要なユーザー権限、アクセス許可、および役割の一覧については [、「Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)のアーカイブの展開」を参照してください。 
  
> [!NOTE]
> Microsoft Exchange 統合を使用する場合、Exchange ポリシーの構成には適切な管理者権限とアクセス許可が必要です。 詳細については、Exchange のドキュメントを参照してください。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ

 Microsoft Exchange 統合を選択した場合は、Exchange のポリシーと構成を使用して Skype for Business Server のアーカイブを制御します。 Microsoft Exchange 統合オプションは、グローバル レベル、サイト レベル、およびプール レベルで構成できます。 展開に複数のフォレストが含まれる場合は、Skype for Business Server と Exchange の間で設定を同期する必要があります。 以下を決定する必要があります。
  
- IM、会議、または両方をアーカイブするかどうか
    
- Skype for Business Server に障害が発生した場合に IM および会議セッションをブロックする重要モードを実装するかどうか 
    
- アーカイブされたデータの保存に Exchange を使用する Microsoft Exchange 統合オプションの選択
    
アーカイブをサポートするために Exchange In-Place 保持ポリシーと設定を構成する方法については、Exchange 製品ドキュメントを参照してください。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server ストレージ

Skype for Business Server ストレージを選択した場合は、Skype for Business Server のアーカイブ ポリシーと構成を使用して、アーカイブの有効化および実装方法を制御します。 Skype for Business Server ストレージは SQL Server データベースを使用します。そのため、適切な SQL Server データベースをトポロジに追加し、アーカイブ ポリシーを構成する必要があります。 
  
### <a name="add-storage-databases-to-your-topology"></a>トポロジにストレージ データベースを追加する

ストレージ データベースSQL Serverトポロジに追加する場合、アーカイブ データベースを次のデータベースと共に作成できます。
  
- 監視データベース
    
- Enterprise Edition フロントエンド プールのバックエンド データベース
    
> [!NOTE]
> アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。 
  
アーカイブ データベースを監視データベース、バック エンド データベース、またはこれらの両方のデータベースと共に使用する場合は、データベースの一部またはすべてに対して単一の SQL インスタンスを使用するか、データベースごとに個別の SQL インスタンスを使用できます。各 SQL インスタンスには、単一のバック エンド データベース、単一の監視データベース、および単一のアーカイブ データベースのみを含めできます。
  
すべてのサーバーの役割とデータベースの一覧の詳細については [、「Topology Basics for Skype for Business Server」を参照してください](../../plan-your-deployment/topology-basics/topology-basics.md)。 記憶域データベースを含むトポロジの更新の詳細については、「Skype for Business Server で新しいトポロジを作成および公開する [」を参照してください](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>アーカイブ オプションとユーザー ポリシーを決定する

以下を決定する必要があります。
  
- 内部通信と外部通信のアーカイブを有効にするか無効にするか
    
- IM、会議、または両方をアーカイブするかどうか
    
- Skype for Business Server に障害が発生した場合に IM および会議セッションをブロックする重要モードを実装するかどうか 
    
- 特定のユーザーとグループに対してポリシーを有効にするかどうか
    
Skype for Business Server のアーカイブ オプションは、次のレベルで指定できます。 
  
- **グローバル レベルのオプションです**。 これは既定のアーカイブ構成であり、展開全体に適用されます。 Skype for Business Server を展開するときに作成され、既定では、内部通信と外部通信の両方のアーカイブが無効になります。 このオプションは削除できません。 削除オプションを選択すると、グローバル オプションは既定の設定にリセットされます。
    
- **サイト レベルのオプション**。 サイトのサイト レベルのアーカイブ オプションを作成および構成することで、1 つ以上の特定のサイトのアーカイブを有効または無効にできます。 作成する任意のサイト レベルのアーカイブ オプションを削除できます。 サイト レベルのアーカイブ オプションはグローバル オプションより優先されますが、このオプションで指定されたサイトに対してだけ優先されます。 
    
    たとえば、グローバル構成で内部通信と外部通信のアーカイブを有効にし、外部通信のアーカイブを無効にするサイト構成を作成した場合、そのサイトでは内部通信だけがアーカイブされます。 別の例として、グローバル構成で IM のアーカイブのみを有効にし、IM と会議の両方のアーカイブを有効にするサイト構成を作成する場合、会議はサイトに対してアーカイブされるだけで、組織の残りの部分ではアーカイブされません。
    
- **プール レベルのオプション**。 個々のプールのプール レベル構成を作成および構成することで、1 つ以上の特定のプールのアーカイブ設定を指定できます。 プール レベルのアーカイブ構成は、作成した場合にのみ存在します。 任意のプール レベルのアーカイブ構成を変更および削除できます。 プール レベルのアーカイブ構成は、グローバル構成および作成したサイト アーカイブ構成より優先されます。 
    
    たとえば、グローバル構成でのみ IM のアーカイブを有効にしてから、IM と会議の両方のアーカイブを有効にするサイト レベルの構成を作成し、IM のアーカイブのみを有効にするプール レベルの構成を作成するとします。 プール レベルの構成で指定されたプールにホームしているユーザーを除く、サイトのすべてのユーザーの IM と会議の両方で通信がアーカイブされます。 組織内の他のすべてのユーザーの場合、アーカイブは IM に対してのみ有効になります。
    
- **ユーザー アーカイブ ポリシー**。 指定したユーザーおよびユーザー グループに対してユーザー レベルのアーカイブ ポリシーを作成、構成、適用することで、1 つ以上の特定のユーザーおよびユーザー グループのアーカイブを有効または無効にできます。 作成したユーザー レベルのアーカイブ ポリシーは削除できます。また、アーカイブ ポリシーを適用するユーザーとユーザーのグループを変更できます。 ユーザー レベルのアーカイブ ポリシーは、グローバル ポリシーとサイト ポリシーより優先されますが、適用されるユーザーおよびユーザー グループに対してのみです。 
    
    たとえば、グローバル構成で内部通信と外部通信のアーカイブを無効にし、内部通信と外部通信のアーカイブを有効にするサイト レベルのポリシーを作成し、外部通信のアーカイブを無効にするユーザー レベルのポリシーを作成するとします。 ユーザー レベルのポリシーを適用するユーザーを除くすべてのサイト ユーザーの外部通信と内部通信の両方で通信がアーカイブされます。これらのユーザーの内部通信だけがアーカイブされます。
    
アーカイブを展開するときに初期アーカイブ構成を設定する方法の詳細については [、「Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)のアーカイブを展開する」を参照してください。 展開後のアーカイブ管理の詳細については、「Skype for Business Server でのアーカイブの [管理」を参照してください](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>アーカイブ構成ツール

 ほとんどのアーカイブ オプションは、Skype for Business Server コントロール パネルを使用して制御します。 ただし、Skype for Business Server 管理シェルを使用する場合にのみ使用できるオプションがいくつか用意されています。 これらのオプションには、重複するメッセージのアーカイブ、アーカイブされたデータのエクスポートが含まれます。 Skype for Business Server コントロール パネルと Skype for Business Server 管理シェルを使用してアーカイブ ポリシーを管理する方法の詳細については [、「Skype for Business Server](../../manage/archiving/archiving.md)でのアーカイブの管理」を参照してください。
  
## <a name="access-archived-data"></a>アーカイブされたデータにアクセスする

アーカイブされたデータへのアクセス方法は、データの保管場所に応じて異なります。 
  
- **Microsoft Exchange ストレージ**。 Exchange 統合オプションを選択した場合、Skype for Business Server は Exchange にホームを置き、メールボックスが In-Place Hold に設定されているすべてのユーザーのアーカイブ コンテンツを Exchange ストアに保管します。 アーカイブされたデータは、ユーザーメールボックスの回復可能なアイテム フォルダーに格納されます。回復可能なアイテム フォルダーは一般にユーザーには表示されません。Exchange **Discovery Management** の役割を持つユーザーだけが検索できます。 Exchange を展開すると、SharePoint と共にフェデレーション検索と検出が有効にされます。 Exchange に格納されているデータのストレージ、保持、検出の詳細については、Exchange と SharePoint のドキュメントを参照してください。
    
- **Skype for Business Server アーカイブ ストレージ**。 Skype for Business Server アーカイブ データベースをセットアップすると、Skype for Business Server は、Exchange にホームではないユーザー、およびメールボックスを In-Place 保留にしていないユーザーのアーカイブ コンテンツを Skype for Business Server アーカイブ データベースに保存します。 このデータは検索できませんが、他のツールを使用して検索可能な形式にエクスポートできます。 アーカイブ データベースに格納されているデータのエクスポートの詳細については、「Skype for Business Server でアーカイブされたデータをエクスポートする [」を参照してください](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>詳細情報

アーカイブの詳細については、以下のトピックを参照してください。
  
- [Skype for Business Server のアーカイブを展開する](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Skype for Business Server でのアーカイブの管理](../../manage/archiving/archiving.md)
    
Skype for Business Server と Exchange の連携の詳細については [、「Skype for Business](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)と Exchange を統合する計画」を参照してください。
  

