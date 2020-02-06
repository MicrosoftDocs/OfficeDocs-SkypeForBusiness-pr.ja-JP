---
title: Skype for Business Server でアーカイブの計画を立てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: '概要: Skype for Business Server でアーカイブの計画を立てる方法については、このトピックを参照してください。'
ms.openlocfilehash: 92658ef139464cacaa7f66abb2cf3aa6294b463b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816086"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Skype for Business Server でアーカイブの計画を立てる
 
**概要:** このトピックでは、Skype for Business Server でアーカイブの計画を立てる方法について説明します。
  
企業やその他の組織には、特定の種類の通信内容を保持するように求める規制が業界や政府機関から多数課せられています。 組織にこのような要件がある場合は、Skype for Business Server のアーカイブ機能を使用して、コンプライアンス要件の一部をサポートするためにインスタントメッセージング (IM) と会議 (会議) 通信をアーカイブすることができます。
  
## <a name="archiving-components"></a>アーカイブ コンポーネント

Skype for Business Server では、次のアーカイブコンポーネントが使用されます。
  
- **アーカイブ エージェント**。 アーカイブ エージェントは、統合データ収集エージェントとも呼ばれ、すべての Enterprise Edition フロントエンド プールと Standard Edition サーバーに自動的にインストールされ、アクティブ化されます。 アーカイブ エージェントは自動的にアクティブ化されますが、アーカイブを有効にし、適切に構成するまで、実際にはメッセージは取得されません。 既定では、アーカイブは無効になっています。
    
- **データストレージのアーカイブ**。 Skype for business server のデータストレージは、Skype for Business Server SQL Server データベースとして実装することも、exchange ストレージと統合されている場合は、Skype for business Server データベースとして実装することもできます。 
    
アーカイブにはファイル ストレージも必要ですが、アーカイブはフロントエンド サーバーまたは Standard Edition サーバーと同じファイル ストレージを使用します。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>アーカイブに対する組織の要件を判別する

アーカイブを実装するには、次のことを確認して、アーカイブに関する組織の要件を満たす方法を決定する必要があります。
  
- **どのストレージ オプションを使用するか**。 次の 2 つの方法のいずれか、または両方を組み合わせてストレージを実装することができます。
    
  - **Exchange ストレージ。** Exchange の展開がある場合は、skype for business server と exchange アーカイブを統合して、Skype for business Server と Exchange のアーカイブデータを Exchange にまとめて保存することができます。 Microsoft Exchange 統合オプションを有効にしている場合、Exchange Server を使用しているユーザーのメールボックスは、アーカイブデータに Exchange ストレージを使用します。ただし、メールボックスがインプレースホールドに置かれている場合のみです。 既定では、Microsoft Exchange の統合は有効ではありません。
    
  - **Skype for Business Server ストレージ。** Exchange を使用していないユーザー、またはメールボックスがインプレースホールドに配置されていないユーザーがいる場合、または展開のいずれかまたはすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合は、S を使用して Skype for Business Server のアーカイブデータベースを展開できます。QL サーバー。
    
- **アーカイブを展開するタイミング**。 初めての Skype for Business Server の展開の一部としてアーカイブを展開することも、既存の展開に追加することもできます。 Skype for Business Server のアーカイブストレージ (SQL Server データベース) を使用するには、トポロジビルダーを使用して、トポロジにデータベースを追加してから、もう一度トポロジを公開します。 すべてのユーザーが Exchange を使用していて、メールボックスがインプレース保持されている場合、トポロジを更新する必要はありませんが、Exchange のアーカイブデータを保存するには Microsoft Exchange 統合を有効にする必要があります。 
    
- **組織内のどのサイトとユーザーでアーカイブを必須とするか**。 組織全体のアーカイブ設定を構成することができます。また、必要に応じて、特定のサイト、プール、ユーザー、ユーザーグループのアーカイブ設定を構成することもできます。
    
- **どのコンテンツをアーカイブするか**。アーカイブの指定を、グローバル レベルで行うか、特定のサイトおよびユーザーを対象として行うかを問わず、これらの各レベルで、次の種類のコンテンツを有効にするかどうかを指定します。 
    
  - ピアツーピアのインスタント メッセージ
    
  - マルチパーティのインスタント メッセージである会議 (ミーティング)
    
  - アップロードされたコンテンツ (配付資料など) およびイベント関連のコンテンツ (参加、退席、アップロード、共有、表示設定の変更など) を含む会議コンテンツ
    
  - 会議中に共有するホワイトボードおよび投票
    
- **アーカイブすることができないコンテンツ**。 次の種類のコンテンツをアーカイブすることはできません。 
    
  - ピアツーピアのファイル転送
    
  - ピアツーピアのインスタント メッセージおよび会議の音声ビデオ
    
  - ピアツーピアのインスタント メッセージおよび会議のデスクトップ/アプリケーション共有
    
    Skype for Business Server では、常設チャットの会話もアーカイブされません。 常設チャットの会話をアーカイブするには、コンプライアンスサービスを有効にして構成する必要があります。これは、常設チャットサーバーで展開できるコンポーネントです。 詳細については、「 [Skype For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を参照してください。

    > [!NOTE] 
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 
    
- **アーカイブされた資料の保持期間**。 アーカイブデータベースは、長期間の保存のためのものではありません。また、Skype for Business Server では、アーカイブデータの電子的な探索 (検索) ソリューションを提供していないため、データを他のストレージに移動する必要があります。 Skype for Business Server には、アーカイブデータのエクスポートに使用できるセッションエクスポートツールが用意されています。これにより、アーカイブデータの検索可能なトランスクリプトが作成されます。 
    
     グローバルポリシーの場合、および作成するサイトとユーザーポリシーのそれぞれについて、アーカイブデータとエクスポートデータをいつ削除するかを指定できます。 データの削除の詳細については、「 [Skype For Business Server でアーカイブデータの削除を管理](../../manage/archiving/purging-of-archived-data.md)する」を参照してください。 セッションエクスポートツールの使用方法の詳細については、「 [Skype For Business Server にアーカイブデータをエクスポート](../../manage/archiving/export-archived-data.md)する」を参照してください。
    
- **内部通信または外部通信をアーカイブするかどうか**。内部通信 (つまり、内部ユーザー間の通信)、外部通信 (少なくとも 1 人の内部ネットワーク外のユーザーが含まれる通信)、または両方のアーカイブを有効にできます。これらのオプションは、組織全体に対して指定することも、特定のサイトおよびプールに対して指定することもできます。既定では、どちらのオプションも無効です。
    
    > [!NOTE]
    > 内部または外部通信のアーカイブの制御は、Skype for Business のポリシーでのみ利用できます。 Exchange と統合されたアーカイブでは、内部通信と外部通信の両方がアーカイブされるか、アーカイブされません。 
  
- **重要モードを実装するかどうか**。 組織のためにアーカイブが要件となっている場合、重要なモードを設定すると、Skype for Business Server に障害が発生したときに、アーカイブを禁止する IM と会議セッションがブロックされます。 次に例を示します。 
    
  - Skype for Business Server ストレージサービスに問題があります。 この場合、アーカイブが有効になっているユーザーに対して IM がブロックされます。
    
  - ファイル共有を使用できない場合や、ストレージ サービスに問題が発生する場合があります。この場合、障害発生時にプール内でホストされているアクティブな会議がすべて制限モードに切り替えられ、新しい会議をアクティブにすることはできません。
    
    障害から回復した後、IM および会議は自動的に回復します。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>アーカイブ展開と構成オプションの選択

サーバーを展開すると、各フロントエンドサーバーに自動的にアーカイブがインストールされますが、構成しないとアーカイブは有効になりません。 アーカイブの構成方法は、展開方法によって決まります。 アーカイブは、次のいずれかの方法で展開できます。
  
- Microsoft Exchange ストレージを使用する
    
- Skype for Business Server ストレージを使用する
    
> [!NOTE]
> Skype for Business Server のアーカイブデータベースと Microsoft Exchange の統合を有効にした場合、Exchange のポリシーは、Skype for business Server のアーカイブポリシーを上書きします。ただし、exchange を使用していて、メールボックスが挿入されているユーザーのみが対象となります。インプレースホールド。 Skype for Business のアーカイブは、Microsoft Exchange のインプレースホールドポリシーによって異なります。 
  
1つのフロントエンドプールまたは Standard Edition サーバー用にアーカイブを展開する場合は、その他のすべてのフロントエンドプールおよび標準エディションのサーバーを展開で有効にする必要があります。 会話や会議がホストされているプールでアーカイブが有効になっていなければ、会議データを完全にアーカイブすることはできません。 IM メッセージにはアーカイブは機能しますが、会議のコンテンツやイベントはアーカイブされません。
  
> [!NOTE]
> Skype for Business Server では、組織のセキュリティ基準を維持しながら管理タスクの委任を有効にするために、役割ベースのアクセス制御 (RBAC) が使用されます。 RBAC を使用すると、定義済みの管理者の役割にユーザーを割り当てることにより、管理者特権が付与されます。 Skype for Business のアーカイブポリシーと構成を構成するには、CsArchivingAdministrator の役割が割り当てられている必要があります (別のコンピューターからのリモートではなく、アーカイブが展開されているサーバーで直接構成が行われている場合を除きます)。). アーカイブ展開に必要なユーザー権利、権限、役割の一覧については、「 [Skype For Business Server のアーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)」をご覧ください。 
  
> [!NOTE]
> Microsoft Exchange の統合を使用している場合、Exchange ポリシーを構成するには、適切な管理者権限と権限が必要です。 詳細については、Exchange のドキュメントを参照してください。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange ストレージ

 Microsoft Exchange の統合を選択する場合は、Exchange のポリシーと構成を使用して、Skype for Business Server のアーカイブを制御します。 Microsoft Exchange 統合オプションは、グローバルレベル、サイトレベル、プールレベルで構成できます。 展開に複数のフォレストが含まれている場合は、Skype for Business Server と Exchange の間で設定を同期する必要があります。 また、次のことを決定する必要があります。
  
- IM、電話会議、またはこの両方をアーカイブするかどうか
    
- Skype for Business Server に障害が発生した場合に、IM と会議セッションをブロックする、重要なモードを実装するかどうか 
    
- アーカイブデータの保存に Exchange を使用する Microsoft Exchange 統合オプションの選択
    
アーカイブをサポートするために Exchange のインプレースホールドポリシーと設定を構成する方法については、「Exchange の製品ドキュメント」を参照してください。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server ストレージ

Skype for Business Server ストレージを選択する場合は、Skype for Business Server のアーカイブポリシーと構成を使用して、アーカイブの有効化と実装方法を管理します。 Skype for Business Server ストレージは SQL Server データベースを使用するため、適切な SQL Server データベースをトポロジに追加してから、アーカイブポリシーを構成する必要があります。 
  
### <a name="add-storage-databases-to-your-topology"></a>トポロジへのストレージ データベースの追加

SQL Server ストレージデータベースをトポロジに追加するときは、次のいずれかを使用してアーカイブデータベースを検索することができます。
  
- 監視データベース
    
- Enterprise Edition フロントエンド プールのバックエンド データベース
    
> [!NOTE]
> アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。 
  
監視データベース、バックエンドデータベース、またはこれら両方のデータベースの両方でアーカイブデータベースを検索する場合は、データベースのいずれかまたはすべてに1つの SQL インスタンスを使用するか、データベースごとに個別の SQL インスタンスを使用することができます。次のような方法があります。制限: 各 SQL インスタンスには、1つのバックエンドデータベース、単一の監視データベース、単一のアーカイブデータベースのみを含めることができます。
  
すべてのサーバーの役割とデータベースの collocation の詳細については、「 [Skype For Business server のトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)」を参照してください。 記憶域データベースを含めるようにトポロジを更新する方法の詳細については、「 [Skype For Business Server で新しいトポロジを作成して発行](../../deploy/install/create-and-publish-new-topology.md)する」を参照してください。
  
### <a name="determine-archiving-options-and-user-policies"></a>アーカイブ オプションとユーザー ポリシーの決定

次のことを決定する必要があります。
  
- 内部通信と外部通信のアーカイブを有効/無効のどちらにするか
    
- IM、電話会議、またはこの両方をアーカイブするかどうか
    
- Skype for Business Server に障害が発生した場合に、IM と会議セッションをブロックする、重要なモードを実装するかどうか 
    
- 特定のユーザーおよびグループのポリシーを有効にするかどうか
    
Skype for Business Server のアーカイブオプションは、次のレベルで指定できます。 
  
- **グローバル レベル オプション**。 既定のアーカイブ構成であり、展開全体に適用されます。 これは、Skype for Business Server を展開したときに作成され、既定では、内部通信と外部通信の両方のアーカイブが無効になります。 このオプションは削除できません。 削除オプションを選択すると、グローバル オプションが既定の設定にリセットされます。
    
- **サイト レベル オプション**。特定のサイトを対象とするサイト レベルのアーカイブ ポリシーを作成し、構成することによって、1 つ以上のサイトでアーカイブを有効または無効にできます。作成したサイトレベルのアーカイブ オプションは削除できます。サイトレベルのアーカイブ オプションは、グローバル オプションよりも優先されますが、そのオプションで指定されたサイトだけが対象となります。 
    
    たとえば、グローバル構成で内部通信と外部通信のアーカイブを有効にし、外部通信のアーカイブを無効にするサイト構成を作成した場合、そのサイトでは内部通信だけがアーカイブされます。また別の例としては、グローバル構成で IM のアーカイブのみを有効にし、IM と会議の両方のアーカイブを有効にするサイト構成を作成した場合、会議はそのサイトでのみアーカイブされ、組織内の他のサイトではアーカイブされません。
    
- **プール レベル オプション**。個別のプールに対してプール レベルの構成を作成および構成することによって、1 つ以上の特定のプールに対してアーカイブ設定を指定できます。プール レベルのアーカイブ構成は、その構成を作成した場合にのみ存在します。任意のプール レベルのアーカイブ構成を変更および削除できます。プール レベルのアーカイブ構成は、グローバル構成、および作成した任意のサイト アーカイブ構成よりも優先されます。 
    
    たとえば、グローバル構成で IM のアーカイブのみを有効にし、IM と会議の両方のアーカイブを有効にするサイトレベルの構成を作成して、IM のアーカイブのみを有効にするプール レベルの構成を作成した場合を考えます。 この場合、プール レベルの構成で指定されたプールに所属するユーザーを除いて、サイトのすべてのユーザーについて IM と会議の両方の通信がアーカイブされます。 組織内のすべての他のユーザーについては、IM のアーカイブのみが有効になります。
    
- **ユーザー アーカイブ ポリシー**。指定したユーザーおよびユーザー グループを対象とするユーザー レベルのアーカイブ ポリシーを作成して構成し、適用することによって、1 人以上の特定のユーザーや 1 つ以上のユーザー グループに対してアーカイブを有効または無効にできます。作成したユーザー レベルのアーカイブ ポリシーは削除できます。また、アーカイブ ポリシーを適用するユーザーおよびユーザー グループを変更することもできます。ユーザーレベルのアーカイブ ポリシーは、グローバル ポリシーおよびすべてのサイト ポリシーよりも優先されますが、そのポリシーが適用されたユーザーおよびユーザー グループだけが対象となります。 
    
    たとえば、グローバル構成で内部通信と外部通信のアーカイブを無効にし、内部通信と外部通信のアーカイブを有効にするサイト レベルのポリシーを作成して、外部通信のアーカイブを無効にするユーザー レベルのポリシーを作成した場合、すべてのサイト ユーザーに対して外部通信と内部通信の両方がアーカイブされます。 ただし、ユーザー レベルのポリシーを適用したユーザーについては、内部通信だけがアーカイブされます。
    
アーカイブを展開するときに最初のアーカイブ構成を設定する方法について詳しくは、「 [Skype For Business Server のアーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)」をご覧ください。 展開後のアーカイブの管理について詳しくは、「 [Skype For Business Server でアーカイブを管理](../../manage/archiving/archiving.md)する」をご覧ください。 
  
## <a name="archiving-configuration-tools"></a>アーカイブ構成ツール

 ほとんどのアーカイブオプションは、Skype for Business Server コントロールパネルを使用して制御できます。 ただし、Skype for Business Server 管理シェルを使用する場合にのみ使用できるいくつかのオプションがあります。 これらのオプションには、重複するメッセージのアーカイブや、アーカイブ済みデータのエクスポートなどが含まれます。 Skype for Business Server コントロールパネルと Skype for Business Server Management Shell を使用してアーカイブポリシーを管理する方法の詳細については、「 [skype For Business server でアーカイブを管理](../../manage/archiving/archiving.md)する」を参照してください。
  
## <a name="access-archived-data"></a>アーカイブされたデータへのアクセス

アーカイブされたデータへのアクセス方法は、データの保管場所に応じて異なります。 
  
- **Microsoft Exchange ストレージ**。 [Exchange 統合] オプションを選択した場合、Skype for Business Server は exchange ストアのアーカイブコンテンツを、Exchange を使用しているすべてのユーザーに対して保存します。また、ユーザーのメールボックスは、インプレースホールドに入れています。 アーカイブされたデータは、ユーザーのメールボックスの [回復可能なアイテム] フォルダーに格納されます。これは通常、ユーザーには見えません。また、Exchange の**検出管理**役割を持つユーザーのみが検索できます。 展開されている場合、SharePoint と共にフェデレーション検索および検出が有効になります。 Exchange に保存されているデータの記憶域、保持、および検出の詳細については、「Exchange と SharePoint のドキュメント」を参照してください。
    
- **Skype For Business Server アーカイブストレージ**。 Skype for business Server のアーカイブデータベースを設定した場合、skype for Business server は、Exchange を使用していないユーザーのために、Skype for business Server アーカイブデータベースのコンテンツをアーカイブします。また、メールボックスがインプレースホールドに組み込まれていない場合。 This data is not searchable, but it can be exported to formats that are searchable using other tools. アーカイブデータベースに格納されているデータのエクスポートの詳細については、「 [Skype For Business Server にアーカイブデータをエクスポート](../../manage/archiving/export-archived-data.md)する」を参照してください。
    
## <a name="for-more-information"></a>関連情報

アーカイブの詳細については、次のトピックを参照してください。
  
- [Skype for Business Server のアーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Skype for Business Server でアーカイブを管理する](../../manage/archiving/archiving.md)
    
Skype for Business Server と Exchange の連携のしくみの詳細については、「 [skype for business と exchange の統合の計画](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)」を参照してください。
  

