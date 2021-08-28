---
title: 応答グループの展開プロセス (Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 展開プロセスと、応答グループの手順をSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 1cb85ac95025b71de8a071758befb5287a6fafa4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620183"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>応答グループの展開プロセス (Skype for Business

展開プロセスと、応答グループの手順をSkype for Business Server エンタープライズ VoIP。

応答グループは、エンタープライズ VoIPヘルプ デスクや顧客サービス デスクなどのエージェントと呼ばれるグループに着信呼び出しをルーティングしてキューに入れ込む機能です。

応答グループで必要なコンポーネントは、エンタープライズ VoIP を展開するときに、フロント エンド サーバーまたは Standard Edition サーバーに自動的にインストールされ、有効にされます。 応答グループをユーザーが利用できるようにするには、エージェント グループ、キュー、およびワークフローを順に構成する必要があります。 さらに、応答グループ管理者は、既存のワークフローの構成を応答グループ マネージャーに委任して、ワークフローとその関連するエージェント グループとキューを変更および再構成できます。

応答グループを構成するには、次の管理役割のうち 1 つ以上のメンバーになる必要があります。

|**Active Directory セキュリティ グループ (1)** <br/> |ワークフローの作成  <br/> |マネージャーの割り当て  <br/> |エージェント、キューの作成/割り当て  <br/> |休日と営業時間の作成/管理  <br/> |ワークフローのアクティブ化/非アクティブ化  <br/> |ワークフローの構成 (IVR またはハント グループ)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** Active Directory ドメイン サービス のユーザー オブジェクトは、指定された Active Directory セキュリティ グループのメンバーである必要があります。 セキュリティ グループにユーザーを追加するための適切なアクセス許可を持つ管理者または他の委任された Active Directory グループ メンバー (たとえば、Administrator、Account Operators) は、リストされているセキュリティ グループまたはグループにユーザー オブジェクトを追加して、ユーザーが一覧表示された機能を実行できる必要があります。 **(2)** CsResponseGroupAdministrator が CsResponseGroupManager に割り当てたワークフローの場合のみ。 **(3)** 応答グループ マネージャーは、現在のマネージャーが既に管理しているワークフローに CsResponseGroupManager の別のメンバーを割り当てできます。 **(4)** CsViewOnlyAdministrator は動詞 "Get" コマンドレットのみを実行できます。

## <a name="response-group-configuration-prerequisites"></a>応答グループ構成の前提条件

応答グループでは、以下のコンポーネントが必要です。

- アプリケーション サービス

- 応答グループ アプリケーション

- 言語パック

- ファイル ストア (オーディオ ファイルを格納)

- Web サービス (応答グループ構成ツールとエージェントのサインインコンソールとサインアウト コンソールを含む)

これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。

応答グループを構成する前に、次のタスクを実行する必要がある場合があります。

- Lync Server 2013 およびサーバーサーバーのユーザーエンタープライズ VoIP。

- Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。

- キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。

### <a name="enabling-users"></a>ユーザーの有効化

応答グループを構成する最初の手順は、エージェント グループを作成します。 エージェント グループを作成する前に、応答グループのエージェントになるユーザーを有効にし、Skype for Businessおよびエンタープライズ VoIP。 通常、ユーザーがサーバー Skype for Businessを有効にすることを、サーバーまたはサーバー Enterprise Edition展開Standard Edition手順です。 ユーザーが Lync [Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)プレビュー Skype for Business有効または無効にするを参照してください。 エンタープライズ VoIP のユーザーの有効化は通常、エンタープライズ VoIP 展開で行うステップです。 詳細については、「ユーザーを[有効にする」を参照エンタープライズ VoIPをSkype for Business Server。](enable-users-for-enterprise-voice.md)

### <a name="complying-with-fips-requirements"></a>FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。

FIPS に準拠するには、Web サービスのインストール後に、アプリケーション レベルの Web.config ファイルを変更して別の暗号化アルゴリズムを使用する必要があります。 ビューステート データを処理 ASP.NET、トリプル データ暗号化標準 (3DES) アルゴリズムを使用する方法を指定する必要があります。 応答グループ アプリケーションの場合、この要件は、応答グループ構成ツールとエージェントのサインインおよびサインアウト コンソールに適用されます。 この要件の詳細については、「ASP.NET 1.1 から ASP.NET 2.0 へのアップグレード後に ViewState が有効になっている ASP.NET Web ページにアクセスすると、エラー メッセージが表示される場合があります」を参照してください。 911722 [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)

Web.config ファイルを変更するには、以下の手順を実行します。

1. メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。

2. [ファイル] Web.configセクションを探  `<system.web>` します。

3. セクションに次  `<machineKey>` のセクションを追加 `<system.web>` します。

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Web.config ファイルを保存します。

5. コマンド プロンプトでインターネット インフォメーション サービスコマンドを実行して、IIS (IIS) サービスを再起動します。

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Yi、Meng、および Zang の文字のサポート

このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。

> [!NOTE]
> Yi、Meng、Zang の各文字が何で、展開にとって重要な理由については、GB18030 文字セットの情報を参照してください [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105)) 。

Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。 各 Rgsconfig データベースの以下の表にある [**名前**] 列の照合順序を変更します。

- dbo。AgentGroups

- dbo。BusinessHours

- dbo。HolidaySets

- dbo。キュー

- dbo。ワークフロー

2008 SQL Server R2 および 2012 SQL Server、次の (アクセントLatin_General_100) 照合順序を使用します。 この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。

照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。 このツールの使用の詳細については、「Using [SQL Server Management Studio」を参照してください](/sql/ssms/sql-server-management-studio-ssms)。 照合順序を変更するには、以下の手順に従います。

1. 表の再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。 詳細については、「 [保存 (許可されない) ダイアログ ボックス」を参照してください](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box)。 列照合順序の設定の詳細については [、「How to: Set Column Collation (Visual Database Tools)」を参照してください](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105))。

2. Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。

3. Rgsconfig データベースで変更したい表を見つけて右クリックし、[**設計**] をクリックします。

4. [**名前**] 列の照合順序を変更して、表を保存します。

## <a name="response-group-deployment-steps"></a>応答グループの展開手順

**応答グループの展開プロセス**

|**フェーズ**|**手順**|**アクセス許可**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|ユーザーがユーザーとSkype for Businessを有効エンタープライズ VoIP  <br/> |ユーザーとユーザーのエージェントになるSkype for Businessをエンタープライズ VoIP。 ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。 通常、ユーザーはサーバーの展開中Skype for Businessまたはサーバー Enterprise Edition Standard Edition有効になります。 ユーザーは、展開中エンタープライズ VoIPにエンタープライズ VoIPされます。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Lync Server 2013 プレビューのユーザーを有効または無効にする](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [ユーザーがユーザーのエンタープライズ VoIPを有効Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|エージェント グループ、キュー、ワークフローから成る応答グループを作成および構成する  <br/> |1. コントロール Skype for Business Serverまたは管理シェルSkype for Business Serverを使用して、次の操作を行います。  <br/> a. エージェント グループを作成して構成する  <br/> b. キューを作成して構成する  <br/> 2. 必要に応じて、Skype for Business Server管理シェルを使用して、定義済みの応答グループの営業時間と休日を作成します。  <br/> 3. 応答グループ構成ツールまたは Skype for Business Server 管理シェルを使用して、カスタム応答グループの営業時間と休日を含むワークフロー (ハント グループまたは対話型音声応答 (IVR) 通話フロー) を作成します。  <br/> [応答グループ構成ツール] には、[コントロール パネル] Skype for Business Serverアクセスできます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[応答グループ エージェント グループの作成](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [応答グループのキューの作成](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [(省略可能)[応答グループの営業時間を定義する] Skype for Business](optional-define-response-group-business-hours.md) <br/> [(省略可能)[応答グループの休日セットを定義する] Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [ワークフローでの応答グループ ワークフローの設計とSkype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|(オプション) アプリケーションレベルの設定をカスタマイズする  <br/> |既定Skype for Business Server管理シェルを使用して、既定の保留音構成、既定の保留音オーディオ ファイル、エージェントリングバック猶予期間、通話コンテキスト構成をカスタマイズします。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[アプリケーション レベルの応答グループの設定を管理するSkype for Business](managing-application-level-response-group-settings.md) <br/> |
|(オプション) 応答グループの管理を委任する  <br/> |ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループ 管理者は、割り当てられた応答グループを構成できます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[役割ベースのアクセス制御の計画](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|応答グループ展開の検証  <br/> |ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が予想どおりに機能していることを確認します。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>ワークフロー作成シナリオの概要

ワークフローを作成する際には、考えられるシナリオとして次の 2 つがあります。

- **管理者がワークフローを作成して構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、ワークフローおよびワークフローの全要素 (エージェント グループ、キュー、休日と営業時間、保留音など) を作成し、アクティブ化します。

- **管理者がワークフローを作成してマネージャーがオプションを構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、プライマリ SIP URI や表示名を定義し、CsResponseGroupManager の役割のメンバーを割り当て、キューの選択とワークフローのアクティブ化を行います。その後、CsResponseGroupManager は、ログオンしてワークフローの構成を編集できます。具体的には、エージェント グループの作成、キューへのグループの割り当て、電話番号、休日と営業時間、保留音などの構成が行えます。

    > [!NOTE]
    > 管理ワークフローを作成する際には、そのワークフローをアクティブなものとして作成する必要があります。アクティブな管理ワークフローは、保存後に変更したり非アクティブにしたりできます。