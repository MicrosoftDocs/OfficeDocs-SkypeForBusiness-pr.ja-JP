---
title: Skype for Business の応答グループの展開プロセス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server の展開プロセスと応答グループのエンタープライズ VoIP。
ms.openlocfilehash: cec795b5215caa81b281379cd4c433563ccebf83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812327"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Skype for Business の応答グループの展開プロセス

Skype for Business Server エンタープライズ VoIP での応答グループの展開プロセスとエンタープライズ VoIP。

応答グループは、エンタープライズ VoIP、ヘルプ デスクや顧客サービス デスクなどのエージェントと呼ばれるユーザー グループに着信呼び出しをルーティングしてキューに入れ込む機能の 1 つです。

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
> **(1)** Active Directory ドメイン サービスのユーザー オブジェクトは、指定された Active Directory セキュリティ グループのメンバーである必要があります。 セキュリティ グループにユーザーを追加するための適切なアクセス許可を持つ管理者または他の委任された Active Directory グループ メンバー (たとえば、Administrator、Account Operators) は、リストされているセキュリティ グループまたはグループにユーザー オブジェクトを追加して、ユーザーが表示された機能を実行できる必要があります。 **(2)** CsResponseGroupAdministrator が CsResponseGroupManager に割り当てたワークフローの場合のみ。 **(3)** 応答グループ マネージャーは、CsResponseGroupManager の別のメンバーを、現在のマネージャーが既に管理しているワークフローに割り当てできます。 **(4)** CsViewOnlyAdministrator は動詞 "Get" コマンドレットのみを実行できます。

## <a name="response-group-configuration-prerequisites"></a>応答グループ構成の前提条件

応答グループでは、以下のコンポーネントが必要です。

- アプリケーション サービス

- 応答グループ アプリケーション

- 言語パック

- ファイル ストア (オーディオ ファイルを格納)

- Web サービス (応答グループ構成ツールとエージェントのサインインおよびサインアウト コンソールを含む)

これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。

応答グループを構成する前に、次のタスクを実行する必要がある場合があります。

- Lync Server 2013 および エンタープライズ VoIP に対してユーザーを有効にします。

- Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。

- キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。

### <a name="enabling-users"></a>ユーザーの有効化

応答グループを構成する最初の手順は、エージェント グループの作成です。 エージェント グループを作成する前に、Skype for Business および エンタープライズ VoIP の応答グループのエージェントになるユーザーを有効にする必要エンタープライズ VoIP。 Skype for Business のユーザーの有効化は、通常、Enterprise Edition サーバーまたは Standard Edition サーバーの展開の手順です。 Skype for Business でユーザーを有効にする方法の詳細については [、「Enable or Disable Users for Lync Server 2013 Preview」を参照してください](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)。 エンタープライズ VoIP のユーザーの有効化は通常、エンタープライズ VoIP 展開で行うステップです。 詳細については [、「Skype for Business Server でユーザーのエンタープライズ VoIPを有効にする」を参照してください](enable-users-for-enterprise-voice.md)。

### <a name="complying-with-fips-requirements"></a>FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。

FIPS に準拠するには、Web サービスのインストール後に、アプリケーション レベルの Web.config ファイルを変更して、別の暗号化アルゴリズムを使用する必要があります。 ビュー状態データを処理ASP.NET、Triple Data Encryption Standard (3DES) アルゴリズムを使用する必要があります。 応答グループ アプリケーションの場合、この要件は応答グループ構成ツールとエージェントのサインインおよびサインアウト コンソールに適用されます。 この要件の詳細については、Microsoft サポート技術情報の記事 911722「ASP.NET 1.1 から ASP.NET 2.0 にアップグレードした後に ViewState が有効になっている ASP.NET Web ページにアクセスすると、エラー メッセージが表示される場合があります。」を参照してください。 [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)

Web.config ファイルを変更するには、以下の手順を実行します。

1. メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。

2. このファイルWeb.configセクションを探  `<system.web>` します。

3. セクションに次  `<machineKey>` のセクションを追加 `<system.web>` します。

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Web.config ファイルを保存します。

5. コマンド プロンプトで次のコマンドを実行して、インターネット インフォメーション サービス (IIS) サービスを再起動します。

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Yi、Meng、および Zang の文字のサポート

このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。

> [!NOTE]
> Yi、Meng、および Zang の文字が何であり、展開にとって重要な理由については、GB18030 文字セットの情報を参照してください [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223) 。

Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。 各 Rgsconfig データベースの以下の表にある [**名前**] 列の照合順序を変更します。

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.キュー

- dbo.ワークフロー

2008 R2 SQL Server 2012 および SQL Server 2012 の場合は、Latin_General_100 (アクセントを区別する) 照合順序を使用します。 この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。

照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。 このツールの使い方の詳細については、「このツールの使用」 [をSQL Server Management Studioしてください](https://go.microsoft.com/fwlink/p/?linkId=196184)。 照合順序を変更するには、以下の手順に従います。

1. 表の再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。 詳細については、「保存 (許可しない) ダイアログ [ボックス」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=196186)。 列の照合順序の設定の詳細については [、「How to: Set Column Collation (Visual Database Tools)」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=196185)。

2. Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。

3. Rgsconfig データベースで変更したい表を見つけて右クリックし、[**設計**] をクリックします。

4. [**名前**] 列の照合順序を変更して、表を保存します。

## <a name="response-group-deployment-steps"></a>応答グループの展開手順

**応答グループの展開プロセス**

|**フェーズ**|**手順**|**アクセス許可**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|Skype for Business と Skype for Business のユーザーを有効エンタープライズ VoIP  <br/> |Skype for Business および Skype for Business のエージェントになるユーザーを有効エンタープライズ VoIP。 ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。 通常、ユーザーは Enterprise Edition または Standard Edition サーバーの展開中に Skype for Business に対して有効になります。 ユーザーは、展開中エンタープライズ VoIPにエンタープライズ VoIPされます。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Lync Server 2013 プレビューのユーザーを有効または無効にする](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Skype for Business Server でエンタープライズ VoIPを有効にする](enable-users-for-enterprise-voice.md) <br/> |
|エージェント グループ、キュー、ワークフローから成る応答グループを作成および構成する  <br/> |1. Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、次の操作を行います。  <br/> a.  エージェント グループを作成して構成する  <br/> b. キューを作成して構成する  <br/> 2. 必要に応じて、Skype for Business Server 管理シェルを使用して、定義済みの応答グループの営業時間と休日を作成します。  <br/> 3. 応答グループ構成ツールまたは Skype for Business Server 管理シェルを使用して、カスタム応答グループの営業時間と休日を含むワークフロー (ハント グループまたは対話型音声応答 (IVR) 通話フロー) を作成します。  <br/> 応答グループ構成ツールには、Skype for Business Server コントロール パネルからアクセスできます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[応答グループ エージェント グループを作成する](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [応答グループのキューの作成](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(省略可能)Skype for Business で応答グループの営業時間を定義する](optional-define-response-group-business-hours.md) <br/> [(省略可能)Skype for Business での応答グループ休日セットの定義](optional-define-response-group-holiday-sets.md) <br/> [Skype for Business での応答グループ ワークフローの設計と作成](designing-and-creating-response-group-workflows.md) <br/> |
|(オプション) アプリケーションレベルの設定をカスタマイズする  <br/> |Skype for Business Server 管理シェルを使用して、既定の保留音構成、既定の保留音オーディオ ファイル、エージェントリングバック猶予期間、通話コンテキスト構成をカスタマイズします。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でのアプリケーション レベルの応答グループ設定の管理](managing-application-level-response-group-settings.md) <br/> |
|(オプション) 応答グループの管理を委任する  <br/> |ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。 応答グループマネージャーは、割り当てられた応答グループを構成できます。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[役割ベースのアクセス制御の計画](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|応答グループ展開の検証  <br/> |ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が予想どおりに機能していることを確認します。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>ワークフロー作成シナリオの概要

ワークフローを作成する際には、考えられるシナリオとして次の 2 つがあります。

- **管理者がワークフローを作成して構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、ワークフローおよびワークフローの全要素 (エージェント グループ、キュー、休日と営業時間、保留音など) を作成し、アクティブ化します。

- **管理者がワークフローを作成してマネージャーがオプションを構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、プライマリ SIP URI や表示名を定義し、CsResponseGroupManager の役割のメンバーを割り当て、キューの選択とワークフローのアクティブ化を行います。その後、CsResponseGroupManager は、ログオンしてワークフローの構成を編集できます。具体的には、エージェント グループの作成、キューへのグループの割り当て、電話番号、休日と営業時間、保留音などの構成が行えます。

    > [!NOTE]
    > 管理ワークフローを作成する際には、そのワークフローをアクティブなものとして作成する必要があります。アクティブな管理ワークフローは、保存後に変更したり非アクティブにしたりできます。


