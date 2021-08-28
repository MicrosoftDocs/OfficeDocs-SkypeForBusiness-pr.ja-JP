---
title: アーカイブの計画を立Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: '概要: このトピックを参照して、アーカイブを計画する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: e9ebe5aa0b2e4e84d436d24f9d8b7db3b450825d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629579"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>アーカイブの計画を立Skype for Business Server
 
**概要:** このトピックでは、アーカイブを計画する方法について説明します。Skype for Business Server。
  
企業やその他の組織には、特定の種類の通信内容を保持するように求める規制が業界や政府機関から多数課せられています。 組織にこのような要件がある場合は、Skype for Business Server でアーカイブを使用して、インスタント メッセージング (IM) および会議 (会議) 通信をアーカイブして、コンプライアンス要件の一部をサポートできます。
  
## <a name="archiving-components"></a>アーカイブ コンポーネント

Skype for Business Serverは、次のアーカイブ コンポーネントを使用します。
  
- **アーカイブ エージェント:** 統合データ収集エージェントとも呼ばれます。 アーカイブ エージェント (統合データ収集エージェントとも呼ばれる) は、すべてのフロントエンド プールおよびサーバー上にEnterprise Edition自動的にStandard Editionされます。 アーカイブ エージェントは自動的にアクティブ化されますが、アーカイブが有効で適切に構成されるまで、メッセージは実際にはキャプチャされません。 既定では、アーカイブは無効になっています。
    
- **アーカイブ データ ストレージ**。 データ ストレージは、Skype for Business ServerデータベースとしてSkype for Business Server SQL Serverしたり、Exchange展開している場合は、Exchange ストレージと統合できます。 
    
アーカイブにはファイルストレージも必要ですが、アーカイブではフロントエンド サーバーまたはサーバーと同じファイル ストレージStandard Editionします。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>アーカイブに関する組織の要件を決定する

アーカイブを実装するには、以下を決定して、アーカイブに関する組織の要件を満たす方法を決定する必要があります。
  
- **使用するストレージ オプション**。 記憶域を実装するには、次の 2 つの方法のいずれかを使用するか、両方を組み合わせて使用します。
    
  - **Exchangeストレージ。** Exchange 展開がある場合は、Skype for Business Server アーカイブと Exchange アーカイブを統合して、Skype for Business Server と Exchange のアーカイブ データを Exchange にまとめて保存できます。 Microsoft Exchange 統合オプションを有効にすると、Exchange Server に保存されているユーザー メールボックスは、アーカイブされたデータに Exchange ストレージを使用しますが、メールボックスが In-Place Hold に置かれた場合にのみ使用されます。 既定では、Microsoft Exchange統合は有効になっていません。
    
  - **Skype for Business Serverストレージ。** Exchange にホームではないユーザー、またはメールボックスを In-Place 保留にしていないユーザーがある場合、または展開内のすべてのユーザーに Microsoft Exchange 統合を使用しない場合は、SQL Server を使用して Skype for Business Server アーカイブ データベースを展開できます。
    
- **アーカイブを展開する場合**。 アーカイブは、最初の展開の一部として展開Skype for Business Server、既存の展開に追加できます。 アーカイブ ストレージSkype for Business Server (SQL Server データベース) を使用するには、トポロジ ビルダーを使用してトポロジにデータベースを追加し、トポロジを再度発行します。 すべてのユーザーが Exchange に保存され、メールボックスを In-Place Hold に設定している場合は、トポロジを更新する必要はなく、microsoft Exchange 統合を有効にしてアーカイブ されたデータを Exchange に保存する必要があります。 
    
- **組織内のアーカイブが必要なサイトとユーザー**。 組織全体および必要に応じて、特定のサイト、プール、ユーザー、およびユーザー グループのアーカイブ設定を構成できます。
    
- **アーカイブする必要があるコンテンツ**。 アーカイブをグローバル レベルで指定するか、特定のサイトとユーザーに対して指定するか、これらの各レベルで、次の種類のコンテンツを有効にするかどうかを指定します。 
    
  - ピアツーピアのインスタント メッセージ
    
  - マルチパーティのインスタント メッセージである会議 (ミーティング)
    
  - アップロードされたコンテンツ (配付資料など) およびイベント関連のコンテンツ (参加、退席、アップロード、共有、表示設定の変更など) を含む会議コンテンツ
    
  - 会議中に共有するホワイトボードおよび投票
    
- **アーカイブできないコンテンツ**。 次の種類のコンテンツはアーカイブできません。 
    
  - ピアツーピア ファイル転送
    
  - ピアツーピアのインスタント メッセージおよび会議の音声ビデオ
    
  - ピアツーピアのインスタント メッセージおよび会議のデスクトップ/アプリケーション共有
    
    Skype for Business Server常設チャットの会話もアーカイブしません。 常設チャットの会話をアーカイブするには、常設チャット サーバーで展開できるコンポーネントであるコンプライアンス サービスを有効にして構成する必要があります。 詳細については[、「Plan for Persistent Chat Server in Skype for Business Server 2015」を参照](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)してください。

    > [!NOTE] 
    > 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 
    
- **アーカイブされた資料を保持する期間**。 アーカイブ データベースは長期的な保持を目的としていないので、Skype for Business Server はアーカイブ されたデータに対する電子探索 (検索) ソリューションを提供しないので、データを他のストレージに移動する必要があります。 Skype for Business Serverには、アーカイブ データのエクスポートに使用できるセッション エクスポート ツールと、アーカイブされたデータの検索可能なトランスクリプトが作成されます。 
    
     グローバル ポリシー、および作成するサイトおよびユーザー ポリシーごとに、アーカイブおよびエクスポートされたデータを削除する場合を指定できます。 データの削除の詳細については、「アーカイブされたデータの削除を管理する」を参照[Skype for Business Server。](../../manage/archiving/purging-of-archived-data.md) セッション エクスポート ツールの使用の詳細については、「アーカイブされたデータをエクスポートする」を参照[Skype for Business Server。](../../manage/archiving/export-archived-data.md)
    
- **内部通信または外部通信をアーカイブするかどうか。** 内部通信 (つまり、内部ユーザー間の通信)、外部通信 (少なくとも 1 人の内部ネットワーク外のユーザーが含まれる通信)、または両方のアーカイブを有効にできます。これらのオプションは、組織全体に対して指定することも、特定のサイトおよびプールに対して指定することもできます。既定では、どちらのオプションも無効です。
    
    > [!NOTE]
    > 内部通信または外部通信のアーカイブの制御は、Skype for Businessポリシーでのみ使用できます。 統合Exchange、内部通信と外部通信の両方がアーカイブまたはアーカイブされません。 
  
- **クリティカル モードを実装するかどうか**。 アーカイブが組織の要件である場合、重要なモードを構成すると、アーカイブを妨げる Skype for Business Server障害が発生した場合に IM セッションと会議セッションがブロックされます。 次に例を示します。 
    
  - ストレージ サービスのSkype for Business Server。 この場合、アーカイブが有効になっているユーザーに対して IM がブロックされます。
    
  - 使用できないファイル共有またはストレージ サービスの問題。 この場合、障害発生時にプールにホストされているすべてのアクティブな会議が制限モードに切り替えられ、新しい会議をアクティブ化できません。
    
    障害から回復した後、IM および会議は自動的に回復します。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>アーカイブの展開と構成オプションの選択

サーバーを展開すると、アーカイブは各フロントエンド サーバーに自動的にインストールされますが、アーカイブは構成するまで有効になりません。 アーカイブの構成方法は、アーカイブの展開方法によって決まります。 アーカイブは、次のいずれかの方法で展開できます。
  
- Microsoft Exchangeストレージを使用する
    
- ストレージSkype for Business Server使用
    
> [!NOTE]
> 両方の Skype for Business Server アーカイブ データベースを実装し、Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは Skype for Business Server アーカイブ ポリシーを上書きしますが、Exchange に自宅にいて、メールボックスを In-Place Hold に置いたユーザーに対してのみです。 Skype for Businessアーカイブは、Microsoft の保留ポリシー Exchange In-Placeによって異なります。 
  
1 つのフロント エンド プールまたは Standard Edition サーバーにアーカイブを展開する場合は、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーでアーカイブを有効にする必要があります。 会話または会議がホストされているプールでアーカイブが有効になっていない場合は、すべての会議データをアーカイブできない可能性があります。 IM メッセージではアーカイブは引き続き機能しますが、会議のコンテンツとイベントはアーカイブできない場合があります。
  
> [!NOTE]
> 組織のセキュリティ標準を維持しながら管理タスクの委任を有効にするには、Skype for Business Serverベースのアクセス制御 (RBAC) を使用します。 RBAC を使用すると、定義済みの管理者の役割にユーザーを割り当てることにより、管理者特権が付与されます。 Skype for Business アーカイブ ポリシーと構成を構成するには、ユーザーを CsArchivingAdministrator 役割に割り当てる必要があります (別のコンピューターからリモートでではなく、アーカイブが展開されているサーバーで構成が直接行われる場合を含む)。 アーカイブ展開に必要なユーザー権限、アクセス許可、および役割の一覧については、「Deploy [archiving for Skype for Business Server」 を参照してください](../../deploy/deploy-archiving/deploy-archiving.md)。 
  
> [!NOTE]
> Microsoft Exchange統合を使用する場合、Exchangeの構成には適切な管理者権限とアクセス許可が必要です。 詳細については、次のドキュメントExchangeしてください。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ

 [Microsoft Exchange統合] を選択した場合は、Exchangeポリシーと構成を使用して、ユーザーのアーカイブをSkype for Business Server。 グローバル レベル、サイト レベル、Exchangeレベルで Microsoft の統合オプションを構成できます。 展開に複数のフォレストが含まれる場合は、設定を複数のフォレストとSkype for Business Server同期Exchange。 次の情報を確認する必要があります。
  
- IM、会議、または両方をアーカイブするかどうか
    
- 重大なモードを実装するかどうか(エラーが発生した場合に IM セッションと会議セッションをSkype for Business Serverする 
    
- アーカイブされたデータのExchangeに使用する Microsoft Exchange統合オプションの選択
    
アーカイブをサポートするために Exchange In-Place保持ポリシーと設定を構成する方法については、「Exchange」を参照してください。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Serverストレージ

ストレージを選択Skype for Business Server、アーカイブ ポリシー Skype for Business Server構成を使用して、アーカイブを有効および実装する方法を制御します。 Skype for Business ServerはデータベースSQL Server使用します。そのため、適切なデータベース データベースをトポロジにSQL Serverし、アーカイブ ポリシーを構成する必要があります。 
  
### <a name="add-storage-databases-to-your-topology"></a>トポロジにストレージ データベースを追加する

ストレージ データベースSQL Serverトポロジに追加する場合は、アーカイブ データベースを次のデータベースと一緒に作成できます。
  
- 監視データベース
    
- Enterprise Edition フロントエンド プールのバックエンド データベース
    
> [!NOTE]
> アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。 
  
アーカイブ データベースを監視データベース、バック エンド データベース、またはこれらの両方のデータベースと照合する場合は、データベースの一部またはすべてに対して 1 つの SQL インスタンスを使用するか、またはデータベースごとに個別の SQL インスタンスを使用できます。各 SQL インスタンスには、1 つのバック エンド データベース、単一の監視データベース、および 1 つのアーカイブ データベースのみを含めできます。
  
すべてのサーバーの役割とデータベースのコロケーションの詳細については[、「Topology Basics for Skype for Business Server」 を参照してください](../../plan-your-deployment/topology-basics/topology-basics.md)。 ストレージ データベースを含むトポロジを更新する方法の詳細については、「Create and publish new topology in [Skype for Business Server」 を参照してください](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>アーカイブ オプションとユーザー ポリシーの決定

次の情報を確認する必要があります。
  
- 内部および外部通信のアーカイブを有効または無効にするかどうか
    
- IM、会議、または両方をアーカイブするかどうか
    
- 重大なモードを実装するかどうか(エラーが発生した場合に IM セッションと会議セッションをSkype for Business Serverする 
    
- 特定のユーザーとグループのポリシーを有効にするかどうか
    
Skype for Business Serverアーカイブ オプションは、次のレベルで指定できます。 
  
- **グローバル レベル オプション**。 これは既定のアーカイブ構成であり、展開全体に適用されます。 既定では、内部通信と外部Skype for Business Serverアーカイブを無効にするときに作成されます。 このオプションは削除できません。 削除オプションを選択すると、グローバル オプションは既定の設定にリセットされます。
    
- **サイト レベルのオプション**。 サイトのサイト レベルのアーカイブ オプションを作成および構成することで、1 つ以上の特定のサイトのアーカイブを有効または無効にできます。 作成するサイト レベルのアーカイブ オプションを削除できます。 サイト レベルのアーカイブ オプションはグローバル オプションより優先されますが、オプションで指定されたサイトに対してだけ優先されます。 
    
    たとえば、グローバル構成で内部通信と外部通信のアーカイブを有効にし、外部通信のアーカイブを無効にするサイト構成を作成すると、そのサイトの内部通信だけがアーカイブされます。 別の例として、グローバル構成で IM のアーカイブのみを有効にし、IM と会議の両方のアーカイブを有効にするサイト構成を作成する場合、会議はサイトに対してアーカイブされるだけで、組織の残りの部分ではアーカイブされません。
    
- **プール レベルのオプション**。 1 つ以上の特定のプールのアーカイブ設定を指定するには、個々のプールのプール レベル構成を作成および構成します。 プール レベルのアーカイブ構成は、作成した場合にのみ存在します。 プール レベルのアーカイブ構成を変更および削除できます。 プール レベルのアーカイブ構成は、グローバル構成および作成したサイト アーカイブ構成より優先されます。 
    
    たとえば、グローバル構成でのみ IM のアーカイブを有効にしてから、IM と会議の両方のアーカイブを有効にするサイト レベル構成を作成し、IM のアーカイブのみを有効にするプール レベル構成を作成するとします。 プール レベルの構成で指定されたプールに含むユーザーを除き、サイトのすべてのユーザーの IM と会議の両方に対して通信がアーカイブされます。 組織内の他のすべてのユーザーの場合、アーカイブは IM でのみ有効になります。
    
- **ユーザー のアーカイブ ポリシー**。 指定したユーザーおよびユーザー グループに対してユーザー レベルのアーカイブ ポリシーを作成、構成、適用することで、1 つ以上の特定のユーザーおよびユーザー グループのアーカイブを有効または無効にできます。 作成したユーザー レベルのアーカイブ ポリシーを削除し、アーカイブ ポリシーが適用されるユーザーとユーザーのグループを変更できます。 ユーザー レベルのアーカイブ ポリシーは、グローバル ポリシーとサイト ポリシーを上書きしますが、ポリシーが適用されるユーザーおよびユーザー グループに対してのみです。 
    
    たとえば、グローバル構成で内部通信と外部通信のアーカイブを無効にし、内部および外部通信のアーカイブを有効にするサイト レベルのポリシーを作成し、外部通信のアーカイブを無効にするユーザー レベルのポリシーを作成するとします。 通信は、ユーザー レベルのポリシーを適用するユーザーを除くすべてのサイト ユーザーの外部通信と内部通信の両方でアーカイブされます。これらのユーザーの場合は、内部通信だけがアーカイブされます。
    
アーカイブを展開するときに初期アーカイブ構成を設定する方法の詳細については、「Deploy archiving for Skype for Business Server」[を参照してください](../../deploy/deploy-archiving/deploy-archiving.md)。 展開後のアーカイブの管理の詳細については、「Manage [archiving in Skype for Business Server」 を参照してください](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>アーカイブ構成ツール

 ほとんどのアーカイブ オプションを制御するには、[コントロール パネル] Skype for Business Serverを使用します。 ただし、管理シェルを使用してのみ使用できるオプションSkype for Business Serverがあります。 これらのオプションには、重複するメッセージのアーカイブとアーカイブされたデータのエクスポートが含まれます。 Skype for Business Server コントロール パネルと Skype for Business Server 管理シェルを使用してアーカイブ ポリシーを管理する方法の詳細については、「Manage [archiving in](../../manage/archiving/archiving.md)Skype for Business Server」を参照してください。
  
## <a name="access-archived-data"></a>アーカイブされたデータにアクセスする

アーカイブされたデータへのアクセス方法は、データの保管場所に応じて異なります。 
  
- **Microsoft Exchange ストレージ**。 Exchange 統合オプションを選択した場合、Skype for Business Server は Exchange ストアにアーカイブ コンテンツを Exchange に保存し、In-Place Hold にメールボックスを置いたすべてのユーザーに保存します。 アーカイブされたデータは、ユーザーのメールボックス回復可能なアイテム フォルダーに格納されます。これは一般にユーザーには表示されませんが、Exchange **検出** 管理の役割を持つユーザーだけが検索できます。 Exchange展開されている場合は、フェデレーション検索と検出とSharePointを有効にできます。 Exchange に格納されているデータの保存、保持、および検出の詳細については、ExchangeおよびSharePointしてください。
    
- **Skype for Business Serverアーカイブ ストレージ**。 Skype for Business Server アーカイブ データベースを設定すると、Skype for Business Server Skype for Business Server アーカイブ データベースにアーカイブ コンテンツがExchange に保存されていないユーザー、およびメールボックスが In-Place Hold に置かれてないユーザーに対して、アーカイブ コンテンツがIn-Place に保存されます。 このデータは検索できませんが、他のツールを使用して検索可能な形式にエクスポートできます。 アーカイブ データベースに格納されているデータのエクスポートの詳細については、「アーカイブ されたデータをアーカイブ データベースにエクスポート[する」をSkype for Business Server。](../../manage/archiving/export-archived-data.md)
    
## <a name="for-more-information"></a>詳細情報

アーカイブの詳細については、次のトピックを参照してください。
  
- [ユーザーのアーカイブを展開Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [アーカイブを管理Skype for Business Server](../../manage/archiving/archiving.md)
    
統合と統合のSkype for Business Server Exchange詳細については、「Plan [to integrate Skype for Business」を参照](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)Exchange。
  

