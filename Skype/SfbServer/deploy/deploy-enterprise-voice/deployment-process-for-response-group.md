---
title: ビジネス用の Skype で応答グループの展開のプロセス
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 展開プロセスとビジネス サーバーのエンタープライズ VoIP の Skype で応答グループの手順を実行します。
ms.openlocfilehash: c6b46aae2a7bcf46bba02780cf04032149ebcba9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981172"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>ビジネス用の Skype で応答グループの展開のプロセス
 
展開プロセスとビジネス サーバーのエンタープライズ VoIP の Skype で応答グループの手順を実行します。
  
応答グループは、ルーティングし、ユーザー、ヘルプ デスクやカスタマー ・ サービス ・ デスクなど、エージェントと呼ばれるグループへの着信呼び出しをキューに配置するエンタープライズ VoIP 機能です。
  
応答のグループに必要なコンポーネントでは、インストールされ、エンタープライズ VoIP を展開する場合、フロント エンド サーバーまたは Standard Edition サーバーに自動的に有効にすることができます。 応答グループをユーザーが利用できるように、エージェント グループ、キュー、およびワークフローを構成する必要があります。 さらに、応答グループの管理者は、応答グループ マネージャーに、変更し、ワークフローとその関連付けられたエージェント グループとキューを再設定した既存のワークフローの構成を委任できます。
  
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
> **(1)** Active Directory ドメイン サービスをユーザー オブジェクトは一覧に指定された Active Directory セキュリティ グループのメンバーである必要があります。 管理者またはその他の代理の Active Directory グループ メンバー (たとえば、管理者は、アカウント オペレーター) は、セキュリティ グループにユーザーを追加するのには適切なアクセス許可を持つようにするのには、一覧表示されているセキュリティ グループまたはユーザーのグループにユーザー オブジェクトを追加する必要があります。機能を実行します。 **(2)** に対してのみ、CsResponseGroupAdministrator が、CsResponseGroupManager に割り当てられているワークフローです。 **(3)** A の応答グループのマネージャーは、既に現在のマネージャーが管理するワークフローに CsResponseGroupManager の他のメンバーを割り当てることができます。 **(4)** CsViewOnlyAdministrator では、動詞"Get"コマンドレットは実行のみできます。
  
## <a name="response-group-configuration-prerequisites"></a>応答グループ構成の前提条件

応答のグループには、次のコンポーネントが必要です。
  
- アプリケーション サービス
    
- 応答グループ アプリケーション
    
- 言語パック
    
- ファイル ストア (オーディオ ファイルを格納)
    
- Web サービス (応答グループ構成ツールおよびエージェントのサインインとサインアウト コンソールが含まれています)
    
エンタープライズ VoIP を展開するときは、既定でインストールのすべてのこれらのコンポーネントが。
  
応答グループを構成する前に次のタスクを実行する必要があります。
  
- ユーザーの Lync Server 2013 とエンタープライズ VoIP を有効にします。
    
- Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。
    
- キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。
    
### <a name="enabling-users"></a>ユーザーの有効化

応答グループを構成する最初の手順は、エージェント グループを作成するのには。 エージェント グループを作成することができます、前に、ビジネスおよびエンタープライズ VoIP の Skype の応答グループのエージェントとなるユーザーを有効にする必要があります。 ビジネス用の Skype のユーザーを有効にすることは、通常、Enterprise Edition サーバーまたは Standard Edition サーバーの展開の手順です。 ビジネス用の Skype のユーザーを有効にする方法の詳細は、[有効または無効にするユーザーが Lync Server 2013 プレビュー](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)を参照してください。 エンタープライズ VoIP に対してユーザーを有効にすることは、通常、エンタープライズ VoIP 展開のステップです。 詳細については、 [Skype のビジネス サーバーでエンタープライズ VoIP のユーザーを有効にする](enable-users-for-enterprise-voice.md)を参照してください。 
  
### <a name="complying-with-fips-requirements"></a>FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。
  
FIPS に準拠するには、Web サービスをインストールした後に、異なる暗号化アルゴリズムを使用するアプリケーション レベルの Web.config ファイルを変更する必要があります。 ASP.NET がビュー ステート データを処理するためのトリプル データ暗号化標準 (3 des) アルゴリズムを使用するを指定する必要があります。 応答グループ アプリケーションは、この要件は応答グループ構成ツールおよびエージェントのサインインとサインアウト コンソールに適用されます。 この要件の詳細は、マイクロソフト サポート技術情報 911722 を参照してください、"する可能性がありますエラー メッセージが表示を ASP.NET 1.1 から ASP.NET 2.0 にアップグレードした後に有効に ViewState を持つ ASP.NET web ページにアクセスするとき」に[https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)。
  
Web.config ファイルを変更するには、以下の手順を実行します。
  
1. メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。
    
2. 、Web.config ファイルを検索します`<system.web>`セクション。
    
3. 次の追加`<machineKey>`セクションで、`<system.web>`のセクション。
    
   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Web.config ファイルを保存します。
    
5. インターネット インフォメーション サービス (IIS) サービスを再起動するには、コマンド プロンプトで次のコマンドを実行します。 
    
   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Yi、Meng、および Zang の文字のサポート

このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。
  
> [!NOTE]
> イ、加須、および Zang の文字とは理由があります、展開する重要な方法については、GB18030 文字セットの情報を参照してください。 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)。 
  
Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。各 Rgsconfig データベースの以下のテーブルにある [**名前**] 列の照合順序を変更します。
  
- dbo.AgentGroups
    
- dbo.BusinessHours
    
- dbo.HolidaySets
    
- dbo.キュー
    
- dbo.ワークフロー
    
SQL Server 2008 R2 および SQL Server 2012 を使用して、Latin_General_100 (アクセントを区別) の照合順序です。 この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。
  
照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。 このツールの使用に関する詳細については、 [「を使用して SQL Server Management Studio」](https://go.microsoft.com/fwlink/p/?linkId=196184)を参照してください。 照合順序を変更するには、以下の手順に従います。
  
1. テーブルの再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。 詳細については、「 [」(使用できません) を保存ダイアログ ボックス」](https://go.microsoft.com/fwlink/p/?linkId=196186). 列の照合順序の設定方法の詳細についてを参照してください["する方法: セットの列の照合順序 (Visual Database Tools)」](https://go.microsoft.com/fwlink/p/?linkId=196185)。
    
2. Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。
    
3. Rgsconfig データベースで変更したいテーブルを見つけて右クリックし、[**設計**] をクリックします。 
    
4. [**名前**] 列の照合順序を変更して、テーブルを保存します。
    
## <a name="response-group-deployment-steps"></a>応答グループの展開手順

**応答グループの展開プロセス**

|**段階**|**手順**|**アクセス許可**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|ビジネスおよびエンタープライズ VoIP の Skype のユーザーを有効にします。  <br/> |ビジネスおよびエンタープライズ VoIP の Skype のエージェントとなるユーザーを有効にします。 ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。 通常、ユーザーは、ビジネスの Skype の Enterprise Edition または Standard Edition サーバーの展開時に有効です。 ユーザーは、エンタープライズ VoIP の展開中にエンタープライズ VoIP に対して有効です。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[有効にするか、Lync Server 2013 プレビューを表示するユーザーを無効にします。](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。](enable-users-for-enterprise-voice.md) <br/> |
|エージェント グループ、キュー、ワークフローから構成される応答グループを作成および構成する  <br/> |1。 には、次のビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype、Skype を使用します。  <br/> a. エージェント グループを作成して構成する  <br/> b. キューを作成して構成する  <br/> 2. 必要に応じて、グループの業務時間や休日の定義済みの応答を作成するのにビジネス サーバー管理シェルの Skype を使用します。  <br/> 3. 使用ワークフロー (ハント グループまたは対話型音声応答 (IVR) 通話フロー) を作成するには、応答グループ構成ツールまたはビジネス サーバー管理シェルの Skype は、カスタムの応答グループ営業時間および休日を含みます。  <br/> Skype を通じてビジネス サーバーのコントロール パネルの応答グループ構成ツールにアクセスできます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[応答グループ エージェント グループを作成します。](http://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [応答グループ キューを作成します。](http://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(省略可能)ビジネス用の Skype を定義する応答グループの営業時間](optional-define-response-group-business-hours.md) <br/> [(省略可能)ビジネス用の Skype を定義する応答グループ休日を設定します。](optional-define-response-group-holiday-sets.md) <br/> [設計とビジネス用の Skype で応答グループ ワークフローを作成します。](designing-and-creating-response-group-workflows.md) <br/> |
|(オプション) アプリケーションレベルの設定をカスタマイズする  <br/> |Skype ビジネス サーバー管理シェルを使用すると、既定の音楽-保留中の構成、既定の音楽-保留中のオーディオ ファイル、エージェント リングバックの猶予期間、および呼び出しのコンテキストの構成をカスタマイズできます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ビジネス用の Skype のアプリケーション レベルの応答グループの設定を管理します。](managing-application-level-response-group-settings.md) <br/> |
|(オプション) 応答グループの管理を委任する  <br/> |ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループ マネージャーは、割り当てられている応答グループを構成できます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ロール ベースのアクセス制御のための計画](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|応答グループ展開を検証する  <br/> |ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が正常に機能していることを確認します。  <br/> |-  <br/> |-  <br/> |
   
## <a name="overview-of-workflow-creation-scenarios"></a>ワークフロー作成のシナリオの概要

ワークフローを作成する際には、考えられるシナリオとして次の 2 つがあります。
  
- **管理者がワークフローを作成して構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、ワークフローおよびワークフローの全要素 (エージェント グループ、キュー、休日と営業時間、保留音など) を作成し、アクティブ化します。
    
- **管理者がワークフローを作成してマネージャーがオプションを構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、プライマリ SIP URI や表示名を定義し、CsResponseGroupManager の役割のメンバーを割り当て、キューの選択とワークフローのアクティブ化を行います。その後、CsResponseGroupManager は、ログオンしてワークフローの構成を編集できます。具体的には、エージェント グループの作成、キューへのグループの割り当て、電話番号、休日と営業時間、保留音などの構成が実行できます。
    
    > [!NOTE]
    > 管理ワークフローを作成する際には、そのワークフローをアクティブなものとして作成する必要があります。アクティブな管理ワークフローは、保存後に変更したり非アクティブにしたりできます。 
  

