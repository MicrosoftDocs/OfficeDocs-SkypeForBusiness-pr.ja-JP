---
title: Skype for Business Server での会議の展開
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
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '概要: Skype for Business Server で会議を展開する方法については、このトピックを参照してください。'
ms.openlocfilehash: d3cb27bff46dfe8d4ebedadd30d7188e44ce3a50
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103873"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>Skype for Business Server での会議の展開

**概要:** Skype for Business Server で会議を展開する方法については、このトピックを参照してください。

Skype for Business Server では、Web 会議、音声ビデオ (音声ビデオ) 会議、ダイヤルイン会議、インスタント メッセージ (IM) 会議の 4 種類の会議を利用できます。 すべての会議の種類を有効にするか、ニーズに応じて 1 つの種類のみを使用できます。

Skype for Business Server を展開すると、IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して新しいトポロジを作成して発行する場合は、次のチェックリストで説明するように、Web、A/V、およびダイヤルイン会議を展開するかどうかを指定します。

- [Web および音声/ビデオ会議の展開チェックリスト](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [ダイヤルイン会議の展開フローチャートとチェックリスト](deploy-conferencing.md#BKMK_DialinConferencing)

会議を展開する前に、次の計画トピックを読む必要があります。

- [Skype for Business Server での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)

- [Skype for Business Server での会議のハードウェアとソフトウェアの要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [Skype for Business Server の会議トポロジを計画する](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [Skype for Business Server でのダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [Skype for Business Server で大規模な会議を計画する](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web および音声/ビデオ会議の展開チェックリスト
<a name="BKMK_ChecklistWebConferencing"> </a>

次の表に、Web およびオーディオ/ビデオ会議を既存のトポロジに展開するために必要な手順の概要を示します。 関連する計画と手順に関するドキュメントへのリンクが含まれています。

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアをインストールする** <br/> |会議は、フロントエンド プールと Standard Edition サーバーのフロント エンド サーバーで実行されます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。  <br/> Web 会議を有効にする場合は、Skype for Business Server が powerPoint プレゼンテーションの共有とレンダリングを処理するために使用される Office Web Apps Server と通信できる必要があります。  <br/> Web 会議の場合は、ファイル ストアとして使用するファイル共有を指定する必要があります。  <br/> Skype for Business クライアントを使用する外部ユーザーが会議に参加を有効にしますか? その場合は、エッジ サーバーを展開する必要があります。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー  <br/> | [Skype for Business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md) <br> [Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server での会議のハードウェアとソフトウェアの要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [Skype for Business Server Office Web Apps サーバーとの統合を構成する](office-web-app-server.md) <br/> [Skype for Business Server でファイル共有を作成する](../../deploy/install/create-a-file-share.md) <br/> [Skype for Business Server 2015 でのエッジ サーバー展開の計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [Skype for Business Server 2015 でのエッジ サーバーの展開](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**会議をサポートするために適切な内部トポロジの作成** <br/> |トポロジ ビルダーを実行して、トポロジに会議を追加し、トポロジを公開する必要があります。  <br/> |トポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウント  <br/> トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Skype for Business Server ファイル ストアで使用するファイル共有に対するフル コントロールアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できます)  <br/> |[Skype for Business Server で新しいトポロジを作成して発行する](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**会議ポリシーと構成設定の構成** <br/> |会議ポリシーと構成設定を構成するには、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShellのみ) または CSAdministrator ロールにユーザーを割り当てる  <br/> |[Skype for Business Server で会議ポリシーを管理する](../../manage/conferencing/conferencing-policies.md) <br/> [Skype for Business Server で会議の構成設定を管理する](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>ダイヤルイン会議の展開フローチャートとチェックリスト
<a name="BKMK_DialinConferencing"> </a>

 ダイヤルイン会議を使用すると、ユーザーは公衆交換電話網 (PSTN) からダイヤルインして音声/ビデオ会議に参加できます。

ダイヤルイン会議に必要なコンポーネントの一部は、電話会議にもエンタープライズ VoIP。 たとえば、エンタープライズ VoIP を展開する場合は、ダイヤルイン会議にも必要な仲介サーバーと PSTN ゲートウェイ --コンポーネントも展開する必要があります。 そのため、ダイヤルイン会議を展開する方法は、ユーザーが新しいソリューションを展開エンタープライズ VoIPです。

ダイヤルイン会議のフローチャートは、ソリューションを展開するかどうかに応じて実行する必要があるエンタープライズ VoIPします。 フローチャートの次の表は、ダイヤルイン会議の展開に必要で推奨される手順の概要を示しています。 関連する計画と手順に関するドキュメントへのリンクも含まれています。 完全なソリューションソリューションの計画のエンタープライズ VoIPについては、「Skype for Business Server でエンタープライズ VoIPソリューションを [計画する」を参照してください](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。

**ダイヤルイン会議のフローチャート**

![ダイヤルイン会議フロー グラフの展開](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**ダイヤルイン会議の展開チェックリスト**

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアをインストールする** <br/> | 会議は、フロントエンド プールと Standard Edition サーバーのフロント エンド サーバーで実行されます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。 <br/>  ダイヤルイン会議を構成する前に、以下がインストールされていることを確認する必要があります。 <br/>  仲介サーバー <br/>  PSTN ゲートウェイ <br/>  統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます) <br/>  会議アテンダント アプリケーション <br/>  会議アナウンス アプリケーション <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー  <br/> |[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server での会議のハードウェアとソフトウェアの要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [Skype for Business Server でのダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [Skype for Business Server の仲介サーバー コンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [Skype for Business Server のトポロジ ビルダーに仲介サーバーを展開する](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**仲介サーバーと PSTN ゲートウェイを含む会議ワークロードを含むトポロジを作成し、フロントエンド プールまたは Standard Edition サーバーを展開する** <br/> |1. トポロジ ビルダーを実行してトポロジを構成します。 トポロジの構成時に、ダイヤルイン会議オプションを選択します。  <br/> 2. トポロジを発行し、フロントエンド プールまたは Standard Edition サーバーを展開します。  <br/> 3. 必要に応じて、スタンドアロンの仲介サーバーを作成し、PSTN ゲートウェイに関連付ける。  <br/> **注:** この手順は、仲介サーバーを展開しないエンタープライズ VoIP Enterprise Edition フロントエンド サーバーまたは Standard Edition サーバーと一緒に配置しない場合にのみ必要です。 サーバーを展開するエンタープライズ VoIP、仲介サーバーと PSTN ゲートウェイをインストールおよび構成して、サーバーの展開の一エンタープライズ VoIPします。 仲介サーバーを照合する場合は、フロント エンド プールまたは Standard Edition サーバー展開の一部として仲介サーバーをインストールして構成します。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> 管理者  <br/> |[Skype for Business Server で新しいトポロジを作成して発行する](../../deploy/install/create-and-publish-new-topology.md) <br/> [Skype for Business Server のトポロジ ビルダーに仲介サーバーを展開する](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**ダイヤル プランを構成する** <br/> |ダイヤル プランは、特定の場所からダイヤルされた電話番号を、電話の承認と通話ルーティングの目的で 1 つの標準 (E.164) 形式に変換する一連の電話番号正規化ルールです。 異なる場所からダイヤルされた同じ電話番号は、それぞれのダイヤル プランに基づいて、各場所に応じて異なる E.164 番号に解決できます。 エンタープライズ VoIP展開する場合は、その展開の一部としてダイヤル プランを設定し、ダイヤル プランがダイヤルイン会議にも対応するようにする必要があります。 会議を展開しないエンタープライズ VoIPダイヤルイン会議のダイヤル プランを設定する必要があります。  <br/> 次のように、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用してダイヤル プランを設定します。  <br/> 1. ダイヤルイン アクセスの電話番号をルーティングする 1 つ以上のダイヤル プランを作成します。  <br/> 2. 各プールに既定のダイヤル プランを割り当てる。 ダイヤル プランを適用する地理的場所に [**ダイヤルイン会議の地域**] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でのダイヤルイン会議の構成](dial-in-conferencing.md) <br/> [Skype for Business Server でダイヤル プランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**ダイヤル プランに地域が割り当てられているか確認する** <br/> |**Get-CsDialPlan** コマンドレットと **Set-CsDialPlan** コマンドレットを実行して、すべてのダイヤル プランに領域が割り当てられているか確認します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でのダイヤルイン会議の構成](dial-in-conferencing.md) <br/> [Skype for Business Server でダイヤル プランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**ダイヤルイン会議をサポートするように会議ポリシーを構成する** <br/> | 会議ポリシーの設定を構成するには、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェル **を使用** します。 次のことを指定します。 <br/>  PSTN 会議ダイヤルインを有効にするかどうか。 <br/>  ユーザーが匿名参加者を招待できるようにするかどうか。 <br/>  認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server で会議ポリシーを管理する](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**ダイヤルイン アクセス番号を構成する** <br/> |Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、ユーザーが電話会議にダイヤルインするために呼び出すダイヤルイン アクセス番号を設定し、アクセス番号を適切なダイヤル プランに関連付ける地域を指定します。 開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。 すべてのアクセス番号は、[ダイヤルイン会議の設定] ページで使用できます。  <br/> **注:** ダイヤルイン アクセス番号を作成した後 **、Set-CsDialInConferencingAccessNumber** コマンドレットを使用して Active Directory 連絡先オブジェクトの表示名を変更し、ユーザーが適切なアクセス番号を簡単に識別できます。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でダイヤル プランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Skype for Business Server でダイヤルイン会議アクセス番号を管理する](../../manage/conferencing/access-numbers.md) <br/> [New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**ユーザー アカウントに回線 URI を割り当てる** <br/> |Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、テレフォニー 回線 **URI** を一意の正規化された電話番号 (tel:+14255550200 など) として構成します。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[ユーザー アカウントに回線 URI を割り当てる](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する** <br/> |会議 PIN ポリシーを表示または変更するには、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを **使用します**。 最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でのダイヤルイン会議の PIN ポリシーの管理](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**(オプション) DTMF コマンドの主要なマッピングを変更する** <br/> |**Set-CsDialinConferencingDtmfConfiguration** コマンドレットを使用して、デュアルトーン多周波数 (DTMF) コマンドに使用されるキーを変更します。参加者は会議の設定 (ミュートやミュート解除、ロック解除など) を制御するために使用できます。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server で DTMF コマンドのキー マッピングを管理する](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**(オプション) 会議の参加時と退席時のアナウンス動作を変更する** <br/> |**Set-CsDialinConferencingConfiguration** を使用して、参加者が会議に参加および退席する際のアナウンス動作を変更します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server で会議への参加と退出のお知らせを管理する](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**(推奨)会議ディレクトリの構成** <br/> |**New-CsConferenceDirectory** コマンドレットを使用して、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成します。 <br/> |RTCUniversalServerAdmins  <br/> |[(推奨)会議ディレクトリの作成](/previous-versions/office/lync-server-2013/recommended-create-conference-directories) <br/> [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の設定の検証** <br/> |**Get-CsDialinConferencingAccessNumber** コマンドレットを使用して、地域が割り当てられていないすべてのアクセス番号に関して使用されるダイヤルイン会議の地域が設定されたダイヤル プランを検索します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[Skype for Business Server でのダイヤルイン会議の構成](dial-in-conferencing.md) <br/> [Skype for Business Server でのダイヤルイン会議のテスト](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の検証** <br/> |**Test-CsDialInConferencing** コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でのダイヤルイン会議のテスト](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する** <br/> |**Set-CsPinSendCAWelcomeMail** スクリプトを使用して、ユーザーの初期 PIN を設定し、初期 PIN と [ダイヤルイン会議の設定] ページへのリンクを含むウェルカム メールを送信します。 <br/> |RTCUniversalServerAdmins  <br/> |[Skype for Business Server でダイヤルイン ユーザーにウェルカム メールを送信する](../../manage/conferencing/welcome-emails.md) <br/> |