---
title: Skype for Business の応答グループの展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Skype for Business Server Enterprise Voice の展開プロセスと応答グループの手順。
ms.openlocfilehash: 810bf635794f58ad8f28295549023a3ef2450f69
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767530"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Skype for Business の応答グループの展開プロセス

Skype for Business Server Enterprise Voice の展開プロセスと応答グループの手順。

[応答グループ] は、ヘルプデスクや顧客サービスデスクなどのエージェントと呼ばれる、着信通話をルーティングしてキューに登録するエンタープライズ Voip 機能です。

エンタープライズボイスの展開時に、応答グループに必要なコンポーネントが、フロントエンドサーバーまたは Standard Edition サーバーにインストールされ、自動的に有効になります。 ユーザーが応答グループを利用できるようにするには、エージェントグループ、[キュー]、[ワークフロー] を構成する必要があります。 さらに、応答グループ管理者は、既存のワークフローの構成を応答グループマネージャーに委任することができます。これにより、ワークフローと関連するエージェントグループおよびキューを変更して再構成することができます。

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
> **(1)** Active Directory ドメインサービスのユーザーオブジェクトは、一覧表示されている指定の active directory セキュリティグループのメンバーである必要があります。 セキュリティグループにユーザーを追加するための適切な権限を持つ管理者またはその他の委任された Active Directory グループのメンバー (管理者、アカウントオペレーターなど) には、ユーザーが次のことをできるように、一覧表示されたセキュリティグループまたはグループにユーザーオブジェクトを追加する必要があります。記載されている関数を実行します。 **(2)** Csresponsegroupadministrator に割り当てられているワークフローのみ。 **(3)** 応答グループマネージャーは、現在の管理者が既に管理しているワークフローに、CsResponseGroupManager の別のメンバーを割り当てることができます。 **(4)** csviewonlyadministrator は動詞 "Get" コマンドレットのみを実行できます。

## <a name="response-group-configuration-prerequisites"></a>応答グループの構成の前提条件

応答グループには次のコンポーネントが必要です。

- アプリケーション サービス

- 応答グループ アプリケーション

- 言語パック

- ファイル ストア (オーディオ ファイルを格納)

- Web サービス (応答グループの構成ツールとエージェントのサインインとサインアウトコンソールが含まれます)

エンタープライズボイスを展開すると、これらのすべてのコンポーネントが既定でインストールされます。

応答グループを構成する前に、次のタスクを実行する必要がある場合があります。

- Lync Server 2013 およびエンタープライズ Voip のユーザーを有効にします。

- Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。

- キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。

### <a name="enabling-users"></a>ユーザーの有効化

応答グループを構成するための最初の手順は、エージェントグループを作成することです。 エージェントグループを作成する前に、Skype for Business およびエンタープライズ Voip の返信グループに対してエージェントとなるユーザーを有効にする必要があります。 Skype for Business のユーザーを有効にするには、通常、Enterprise Edition server または Standard Edition server の展開の手順を実行します。 Skype for Business ユーザーの有効化の詳細については、「 [Lync Server 2013 プレビューのユーザーを有効または無効](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)にする」を参照してください。 エンタープライズ Voip のユーザーを有効にするには、通常、エンタープライズ Voip 展開の手順を使用します。 詳細については、「 [Skype For Business Server でエンタープライズ voip のユーザーを有効にする](enable-users-for-enterprise-voice.md)」を参照してください。

### <a name="complying-with-fips-requirements"></a>FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。

FIPS に準拠するには、Web サービスをインストールした後に別の暗号化アルゴリズムを使用するようにアプリケーションレベルの web.config ファイルを変更する必要があります。 ASP.NET で、トリプルデータ暗号化標準 (3DES) アルゴリズムを使ってビューステートデータを処理するように指定する必要があります。 応答グループアプリケーションの場合、この要件は、応答グループ構成ツールと、エージェントのサインインとサインアウトコンソールに適用されます。 この要件の詳細については、「Microsoft サポート技術情報の記事 911722 "ASP.NET 1.1 から ASP.NET 2.0" にアップグレードした後に ViewState が有効になっている ASP.NET web ページに[https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)アクセスすると、エラーメッセージが表示されることがあります。

Web.config ファイルを変更するには、以下の手順を実行します。

1. メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。

2. Web.config ファイルで、 `<system.web>`セクションを見つけます。

3. `<system.web>`セクションのに次`<machineKey>`のセクションを追加します。

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Web.config ファイルを保存します。

5. コマンドプロンプトで次のコマンドを実行して、インターネットインフォメーションサービス (IIS) サービスを再起動します。

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Yi、Meng、および Zang の文字のサポート

このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。

> [!NOTE]
> Yi、Meng、および Zang 文字の概要と、それらが展開にとって重要である理由については、「GB18030 文字セット[https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)」の情報を参照してください。

Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。各 Rgsconfig データベースの以下のテーブルにある [**名前**] 列の照合順序を変更します。

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

SQL Server 2008 R2 および SQL Server 2012 の場合は、Latin_General_100 (アクセントによる) 照合順序を使用します。 この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。

照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。 このツールの使用方法の詳細については、「 [SQL Server Management Studio の使用」](https://go.microsoft.com/fwlink/p/?linkId=196184)を参照してください。 照合順序を変更するには、以下の手順に従います。

1. テーブルの再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。 詳細については、「[保存 (許可されていない) ダイアログボックス](https://go.microsoft.com/fwlink/p/?linkId=196186)」を参照してください。 列の照合順序の設定の詳細については、 [「方法: 列の照合順序を設定する (Visual Database Tools)」](https://go.microsoft.com/fwlink/p/?linkId=196185)を参照してください。

2. Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。

3. Rgsconfig データベースで変更したいテーブルを見つけて右クリックし、[**設計**] をクリックします。

4. [**名前**] 列の照合順序を変更して、テーブルを保存します。

## <a name="response-group-deployment-steps"></a>応答グループの展開手順

**応答グループの展開プロセス**

|**段階**|**手順**|**アクセス許可**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|Skype for Business およびエンタープライズ Voip のユーザーを有効にする  <br/> |Skype for Business およびエンタープライズ Voip の担当者になるユーザーを有効にします。 ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。 通常、ユーザーは Enterprise Edition または Standard Edition server の展開時に Skype for Business を有効にしています。 エンタープライズボイスの展開中に、ユーザーはエンタープライズ Voip に対応しています。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Skype for Business Server でエンタープライズ Voip のユーザーを有効にする](enable-users-for-enterprise-voice.md) <br/> |
|エージェント グループ、キュー、ワークフローから構成される応答グループを作成および構成する  <br/> |1. Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、次の操作を行います。  <br/> a. エージェント グループを作成して構成する  <br/> b. キューを作成して構成する  <br/> 2. 必要に応じて、Skype for Business Server 管理シェルを使用して、定義済みの応答グループの勤務時間と休日を作成します。  <br/> 3. 返信グループの構成ツールまたは Skype for Business Server 管理シェルを使用して、カスタム応答グループの営業時間や休日などのワークフロー (ハントグループまたはインタラクティブな音声応答 (IVR) 通話フロー) を作成します。  <br/> Skype for Business Server コントロールパネルから応答グループの構成ツールにアクセスできます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [省略Skype for Business で応答グループの勤務時間を定義する](optional-define-response-group-business-hours.md) <br/> [省略Skype for Business で応答グループの休日セットを定義する](optional-define-response-group-holiday-sets.md) <br/> [Skype for Business での応答グループワークフローの設計と作成](designing-and-creating-response-group-workflows.md) <br/> |
|(オプション) アプリケーションレベルの設定をカスタマイズする  <br/> |Skype for Business Server 管理シェルを使用して、既定の音楽保留の構成、既定の音楽の保留中のオーディオファイル、エージェント ringback の猶予期間、通話コンテキストの構成をカスタマイズします。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のアプリケーションレベル応答グループの設定を管理する](managing-application-level-response-group-settings.md) <br/> |
|(オプション) 応答グループの管理を委任する  <br/> |ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループマネージャーは、それらに割り当てられた応答グループを構成できます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|応答グループ展開を検証する  <br/> |ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が正常に機能していることを確認します。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>ワークフロー作成のシナリオの概要

ワークフローを作成する際には、考えられるシナリオとして次の 2 つがあります。

- **管理者がワークフローを作成して構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、ワークフローおよびワークフローの全要素 (エージェント グループ、キュー、休日と営業時間、保留音など) を作成し、アクティブ化します。

- **管理者がワークフローを作成してマネージャーがオプションを構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、プライマリ SIP URI や表示名を定義し、CsResponseGroupManager の役割のメンバーを割り当て、キューの選択とワークフローのアクティブ化を行います。その後、CsResponseGroupManager は、ログオンしてワークフローの構成を編集できます。具体的には、エージェント グループの作成、キューへのグループの割り当て、電話番号、休日と営業時間、保留音などの構成が実行できます。

    > [!NOTE]
    > 管理ワークフローを作成する際には、そのワークフローをアクティブなものとして作成する必要があります。アクティブな管理ワークフローは、保存後に変更したり非アクティブにしたりできます。


