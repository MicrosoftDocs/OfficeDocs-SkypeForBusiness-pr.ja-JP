---
title: 会議を展開するSkype for Business Server
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
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '概要: このトピックを参照して、会議を展開する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 6c0b1493810bd3e2604621773cd74b490d2bf04e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011571"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>会議を展開するSkype for Business Server

**概要:** このトピックでは、会議を展開する方法について説明します。Skype for Business Server。

Skype for Business Server では、web 会議、音声ビデオ (A/V) 会議、ダイヤルイン会議、インスタント メッセージ (IM) 会議の 4 種類の会議を利用できます。 すべての会議の種類を有効にするか、ニーズに応じて 1 つの種類のみを使用できます。

クライアントを展開するとSkype for Business Server IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して新しいトポロジを作成して発行する場合は、次のチェックリストで説明するように、Web、A/V、およびダイヤルイン会議を展開するかどうかを指定します。

- [Web および音声/ビデオ会議の展開チェックリスト](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [ダイヤルイン会議の展開フローチャートとチェックリスト](deploy-conferencing.md#BKMK_DialinConferencing)

会議を展開する前に、次の計画トピックを読む必要があります。

- [会議の計画を立Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md)

- [会議のハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [電話会議のトポロジを計画Skype for Business Server](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [会議でダイヤルイン会議を計画Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [大規模な会議を計画Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web および音声/ビデオ会議の展開チェックリスト
<a name="BKMK_ChecklistWebConferencing"> </a>

次の表に、Web およびオーディオ/ビデオ会議を既存のトポロジに展開するために必要な手順の概要を示します。 関連する計画と手順に関するドキュメントへのリンクが含まれています。

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアをインストールする** <br/> |会議は、フロントエンド プールのフロント エンド サーバーおよびサーバー上でStandard Editionされます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。  <br/> Web 会議を有効にする場合は、Skype for Business Server が Office Web Apps Server と通信し、PowerPoint プレゼンテーションの共有とレンダリングを処理する必要があります。  <br/> Web 会議の場合は、ファイル ストアとして使用するファイル共有を指定する必要があります。  <br/> クライアントが会議に参加する外部ユーザー Skype for Businessを有効にしますか? その場合は、エッジ サーバーを展開する必要があります。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー  <br/> | [2019 年のサーバー Skype for Business Server要件](../../../SfBServer2019/plan/system-requirements.md) <br> [2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015 年の環境Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [会議のハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [Web Apps Server Officeとの統合を構成Skype for Business Server](office-web-app-server.md) <br/> [ファイル共有を作成するSkype for Business Server](../../deploy/install/create-a-file-share.md) <br/> [2015 年のエッジ サーバーの展開Skype for Business Serverする](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [2015 年にエッジ Skype for Business Serverを展開する](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**会議をサポートするために適切な内部トポロジの作成** <br/> |トポロジ ビルダーを実行して、トポロジに会議を追加し、トポロジを公開する必要があります。  <br/> |トポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウント  <br/> トポロジを発行するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Skype for Business Server ファイル ストアに使用するファイル共有に対する完全な制御アクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できます)  <br/> |[新しいトポロジを作成し、Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**会議ポリシーと構成設定の構成** <br/> |会議Skype for Business Server構成設定を構成Skype for Business Serverコントロール パネルまたは管理シェルを使用します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShellのみ) または CSAdministrator ロールにユーザーを割り当てる  <br/> |[会議ポリシーを管理Skype for Business Server](../../manage/conferencing/conferencing-policies.md) <br/> [会議の構成設定を管理Skype for Business Server](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>ダイヤルイン会議の展開フローチャートとチェックリスト
<a name="BKMK_DialinConferencing"> </a>

 ダイヤルイン会議を使用すると、ユーザーは公衆交換電話網 (PSTN) からダイヤルインして音声/ビデオ会議に参加できます。

ダイヤルイン会議に必要な一部のコンポーネントは、電話会議にもエンタープライズ VoIP。 たとえば、エンタープライズ VoIP を展開する場合は、ダイヤルイン会議にも必要な仲介サーバーと PSTN ゲートウェイ --コンポーネントも展開する必要があります。 したがって、ダイヤルイン会議を展開する方法は、ユーザーが新しいソリューションを展開エンタープライズ VoIPです。

ダイヤルイン会議のフローチャートは、ソリューションを展開するかどうかに応じて、従う必要があるエンタープライズ VoIPします。 フローチャートの次の表は、ダイヤルイン会議の展開に必要で推奨される手順の概要を示しています。 関連する計画と手順に関するドキュメントへのリンクも含まれています。 完全なソリューションの計画の詳細については、「エンタープライズ VoIPソリューションを計画する」をエンタープライズ VoIPを[参照Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)

**ダイヤルイン会議のフローチャート**

![ダイヤルイン会議フロー グラフを展開します。](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**ダイヤルイン会議の展開チェックリスト**

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアをインストールする** <br/> | 会議は、フロントエンド プールのフロント エンド サーバーおよびサーバー上でStandard Editionされます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。 <br/>  ダイヤルイン会議を構成する前に、以下がインストールされていることを確認する必要があります。 <br/>  仲介サーバー <br/>  PSTN ゲートウェイ <br/>  統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます) <br/>  会議アテンダント アプリケーション <br/>  会議アナウンス アプリケーション <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー  <br/> |[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015 年の環境Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [会議のハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [会議でダイヤルイン会議を計画Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [仲介サーバー コンポーネント (Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [サーバー内のトポロジ ビルダーに仲介サーバーを展開Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [[トポロジ ビルダー] でゲートウェイを定義Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**仲介サーバーと PSTN ゲートウェイを含む会議ワークロードを含むトポロジを作成し、フロントエンド プールまたはサーバーをStandard Editionする** <br/> |1. トポロジ ビルダーを実行してトポロジを構成します。 トポロジの構成時に、ダイヤルイン会議オプションを選択します。  <br/> 2. トポロジを発行し、フロントエンド プールまたはサーバーを展開Standard Editionします。  <br/> 3. 必要に応じて、スタンドアロンの仲介サーバーを作成し、PSTN ゲートウェイに関連付ける。  <br/> **注:** この手順は、仲介サーバーを展開しない場合エンタープライズ VoIP、仲介サーバーを Enterprise Edition フロント エンド サーバーまたはStandard Editionします。 サーバーを展開するエンタープライズ VoIP、仲介サーバーと PSTN ゲートウェイをインストールおよび構成し、その展開の一エンタープライズ VoIPします。 仲介サーバーを照合する場合は、仲介サーバーをフロント エンド プールまたはサーバー展開の一部としてインストールStandard Edition構成します。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> 管理者  <br/> |[新しいトポロジを作成し、Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md) <br/> [サーバー内のトポロジ ビルダーに仲介サーバーを展開Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [[トポロジ ビルダー] でゲートウェイを定義Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**ダイヤル プランを構成する** <br/> |ダイヤル プランは、特定の場所からダイヤルされた電話番号を、電話の承認と通話ルーティングの目的で 1 つの標準 (E.164) 形式に変換する一連の電話番号正規化ルールです。 異なる場所からダイヤルされた同じ電話番号は、それぞれのダイヤル プランに基づいて、各場所に応じて異なる E.164 番号に解決できます。 エンタープライズ VoIP展開する場合は、その展開の一部としてダイヤル プランを設定し、ダイヤル プランがダイヤルイン会議にも対応するようにする必要があります。 ダイヤルイン会議を展開エンタープライズ VoIP、ダイヤルイン会議のダイヤル プランを設定する必要があります。  <br/> 次のようにSkype for Business Serverコントロール パネルまたは Skype for Business Server管理シェルを使用してダイヤル プランを設定します。  <br/> 1. ダイヤルイン アクセスの電話番号をルーティングする 1 つ以上のダイヤル プランを作成します。  <br/> 2. 各プールに既定のダイヤル プランを割り当てる。 ダイヤル プランを適用する地理的場所に [**ダイヤルイン会議の地域**] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[会議でダイヤルイン会議を構成Skype for Business Server](dial-in-conferencing.md) <br/> [ダイヤル プランを作成または変更するには、Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**ダイヤル プランに地域が割り当てられているか確認する** <br/> |**Get-CsDialPlan** コマンドレットと **Set-CsDialPlan** コマンドレットを実行して、すべてのダイヤル プランに領域が割り当てられているか確認します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[会議でダイヤルイン会議を構成Skype for Business Server](dial-in-conferencing.md) <br/> [ダイヤル プランを作成または変更するには、Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**ダイヤルイン会議をサポートするように会議ポリシーを構成する** <br/> | 会議Skype for Business Server設定を構成するには、Skype for Business Serverコントロール パネルまたは管理シェルSkype for Business Server **を使用** します。 次のことを指定します。 <br/>  PSTN 会議ダイヤルインを有効にするかどうか。 <br/>  ユーザーが匿名参加者を招待できるようにするかどうか。 <br/>  認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[会議ポリシーを管理Skype for Business Server](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**ダイヤルイン アクセス番号を構成する** <br/> |Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、ユーザーが電話会議にダイヤルインするために呼び出すダイヤルイン アクセス番号を設定し、アクセス番号を適切なダイヤル プランに関連付ける地域を指定します。 開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。 すべてのアクセス番号は、[ダイヤルイン会議] ページ設定できます。  <br/> **注:** ダイヤルイン アクセス番号を作成した後 **、Set-CsDialInConferencingAccessNumber** コマンドレットを使用して Active Directory 連絡先オブジェクトの表示名を変更し、ユーザーが適切なアクセス番号を簡単に識別できます。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ダイヤル プランを作成または変更するには、Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [ダイヤルイン会議のアクセス番号を管理Skype for Business Server](../../manage/conferencing/access-numbers.md) <br/> [New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**ユーザー アカウントに回線 URI を割り当てる** <br/> |テレフォニー Skype for Business Serverコントロール パネルまたは Skype for Business Server管理シェルを使用して、テレフォニー **回線 URI** を一意の正規化された電話番号 (たとえば) として構成します `tel:+14255550200` 。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[ユーザー アカウントに回線 URI を割り当てる](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する** <br/> |会議 PIN Skype for Business Serverを表示または変更Skype for Business Serverコントロール パネルまたは管理シェルを **使用します**。 最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ダイヤルイン会議の PIN ポリシーを管理する (Skype for Business Server](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**(オプション) DTMF コマンドの主要なマッピングを変更する** <br/> |**Set-CsDialinConferencingDtmfConfiguration** コマンドレットを使用して、デュアルトーン多周波数 (DTMF) コマンドに使用されるキーを変更します。参加者は会議の設定 (ミュートやミュート解除、ロック解除など) を制御するために使用できます。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[DTMF コマンドのキー マッピングを管理Skype for Business Server](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**(オプション) 会議の参加時と退席時のアナウンス動作を変更する** <br/> |**Set-CsDialinConferencingConfiguration** を使用して、参加者が会議に参加および退席する際のアナウンス動作を変更します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[会議への参加を管理し、会議のアナウンスをSkype for Business Server](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**(推奨)会議ディレクトリの構成** <br/> |**New-CsConferenceDirectory** コマンドレットを使用して、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成します。 <br/> |RTCUniversalServerAdmins  <br/> |[(推奨)会議ディレクトリの作成](/previous-versions/office/lync-server-2013/recommended-create-conference-directories) <br/> [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の設定の検証** <br/> |**Get-CsDialinConferencingAccessNumber** コマンドレットを使用して、地域が割り当てられていないすべてのアクセス番号に関して使用されるダイヤルイン会議の地域が設定されたダイヤル プランを検索します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[会議でダイヤルイン会議を構成Skype for Business Server](dial-in-conferencing.md) <br/> [電話でのダイヤルイン会議のSkype for Business Server](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の検証** <br/> |**Test-CsDialInConferencing** コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でのダイヤルイン会議のテスト](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する** <br/> |**Set-CsPinSendCAWelcomeMail** スクリプトを使用して、ユーザーの初期 PIN を設定し、初期 PIN と [ダイヤルイン会議の設定] ページへのリンクを含むウェルカム メールを送信します。 <br/> |RTCUniversalServerAdmins  <br/> |[Skype for Business Server でダイヤルイン ユーザーにウェルカム メールを送信する](../../manage/conferencing/welcome-emails.md) <br/> |