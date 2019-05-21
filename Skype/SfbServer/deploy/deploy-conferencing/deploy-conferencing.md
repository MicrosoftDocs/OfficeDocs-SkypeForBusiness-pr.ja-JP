---
title: Skype for Business Server で会議を展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '概要: Skype for Business Server で会議を展開する方法については、このトピックを参照してください。'
ms.openlocfilehash: 08cdf52815b7a3ce2b768520f269abfa4be41279
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276387"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>Skype for Business Server で会議を展開する

**概要:** このトピックでは、Skype for Business Server で会議を展開する方法について説明します。

Skype for Business Server で使用できる会議には、web 会議、音声およびビデオ (A/V) 会議、ダイヤルイン会議、インスタントメッセージ (IM) 会議の4種類があります。 必要に応じて、すべての会議の種類を有効にするか、1つの種類のみを使用するかを選ぶことができます。

Skype for Business Server を展開すると、IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して新しいトポロジを作成および公開するときに、次のチェックリストで説明するように、Web、A/V、ダイヤルインの各会議を展開するかどうかを指定します。

- [Deployment checklist for web and audio/video conferencing](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [ダイヤルイン会議の展開に関するフローチャートとチェックリスト](deploy-conferencing.md#BKMK_DialinConferencing)

会議を展開する前に、次の計画トピックを参照してください。

- [Skype for Business Server での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)

- [Skype for Business Server での会議のハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [Skype for Business Server の会議トポロジを計画する](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [Skype for Business Server でのダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [Skype for Business Server での大規模な会議の計画](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web 会議と音声ビデオ会議の展開チェックリスト
<a name="BKMK_ChecklistWebConferencing"> </a>

次の表に、既存のトポロジに Web 会議と音声ビデオ会議を展開するために必要なステップの概要を示します。 関連する計画および手順に関するドキュメントへのリンクも掲載します。

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |会議は、フロントエンドプールと Standard Edition サーバーのフロントエンドサーバー上で実行されます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。  <br/> Web 会議を有効にしている場合は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために使用される Office Web Apps サーバーと Skype for Business Server が通信できることを確認する必要があります。  <br/> Web 会議に関して、ファイル ストアとして使用するファイル共有も指定する必要があります。  <br/> Skype for Business クライアントの外部ユーザーが、会議に参加できるようにする必要がありますか。参加を許可する場合は、エッジ サーバーを展開する必要があります。  <br/> |ローカル Administrators グループのメンバーであるドメイン ユーザー  <br/> | [Skype for Business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md) <br> [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server での会議のハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [Skype for Business Server の Office Web Apps サーバーとの統合を構成する](office-web-app-server.md) <br/> [Skype for Business Server でファイル共有を作成する](../../deploy/install/create-a-file-share.md) <br/> [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [Skype for Business Server 2015 でのエッジ サーバーの展開](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**会議をサポートするために適切な内部トポロジの作成** <br/> |トポロジに会議を追加するには、トポロジビルダーを実行してから、トポロジを公開する必要があります。  <br/> |トポロジを定義するには、ローカル Users グループのメンバーであるアカウント  <br/> トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Skype for Business Server ファイルストアで使用されるファイル共有に対してフルコントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーは必要な Dacl を構成できます)  <br/> |[Skype for Business Server で新しいトポロジを作成して公開する](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**会議ポリシーと構成設定の構成** <br/> |Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、会議のポリシーと構成設定を構成します。  <br/> |RTCUniversalServerAdmins group (Windows PowerShell のみ) またはユーザーを CSAdministrator ロールに割り当てる  <br/> |[Skype for Business Server の会議ポリシーを管理する](../../manage/conferencing/conferencing-policies.md) <br/> [Skype for Business Server で会議の構成設定を管理する](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>ダイヤルイン会議の展開に関するフローチャートとチェックリスト
<a name="BKMK_DialinConferencing"> </a>

 ダイヤルイン会議を使用すると、ユーザーが公衆交換電話網 (PSTN) を使用して、音声ビデオ会議にダイヤルインできます。

ダイヤルイン会議に必要なコンポーネントの一部は、エンタープライズ Voip でも使用されます。 たとえば、エンタープライズ Voip を展開している場合は、また、ダイヤルイン会議にも必要な仲介サーバーと PSTN ゲートウェイも展開する必要があります。 このため、ダイヤルイン会議の展開方法は、エンタープライズ Voip ソリューションを展開しているかどうかによって異なります。

このダイヤルイン会議のフローチャートでは、エンタープライズ VoIP ソリューションも展開するかどうかに応じて、従う必要のある手順を示します。 フローチャートの後の表では、ダイヤルイン会議を展開する際に必須の手順と推奨される手順の概要を示します。 関連する計画および手順に関するドキュメントへのリンクも掲載します。 完全なエンタープライズ Voip ソリューションの計画について詳しくは、「 [Skype For Business Server でのエンタープライズ voip ソリューションの計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)」をご覧ください。

**ダイヤルイン会議の展開フローチャート**

![ダイヤル会議のフロー チャートを展開する](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**ダイヤルイン会議の展開チェックリスト**

|**段階**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> | 会議は、フロントエンドプールと Standard Edition サーバーのフロントエンドサーバー上で実行されます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。 <br/>  ダイヤルイン会議を構成する前に、次のものがインストールされていることを確認する必要があります。 <br/>  仲介サーバー <br/>  PSTN ゲートウェイ <br/>  統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます) <br/>  会議アテンダント アプリケーション <br/>  会議アナウンス アプリケーション <br/> |ローカル Administrators グループのメンバーであるドメイン ユーザー  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server での会議のハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [Skype for Business Server でのダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [Skype for Business Server の仲介サーバーコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [Skype for Business Server でのトポロジビルダーへの仲介サーバーの展開](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [Skype for Business Server のトポロジビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**仲介サーバーと PSTN ゲートウェイなどの会議のワークロードを含むトポロジを作成して、フロントエンドプールまたは Standard Edition サーバーを展開する** <br/> |1. トポロジビルダーを実行してトポロジを構成します。 トポロジの構成時に、ダイヤルイン会議オプションを選択します。  <br/> 2. トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーを展開します。  <br/> 3. 必要に応じて、スタンドアロンの仲介サーバーを作成して、PSTN ゲートウェイに関連付けます。  <br/> **注:** この手順は、エンタープライズボイスを展開せず、Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーで仲介サーバーを検索しない場合にのみ必要です。 エンタープライズ Voip を展開する場合は、エンタープライズ Voip 展開の一部として、仲介サーバーと PSTN ゲートウェイをインストールして構成します。 仲介サーバーを検索する場合は、フロントエンドプールまたは Standard Edition サーバーの展開の一部として、仲介サーバーをインストールして構成します。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> Administrator  <br/> |[Skype for Business Server で新しいトポロジを作成して公開する](../../deploy/install/create-and-publish-new-topology.md) <br/> [Skype for Business Server でのトポロジビルダーへの仲介サーバーの展開](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [Skype for Business Server のトポロジビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**Configure dial plans** <br/> |ダイヤルプランとは、特定の場所からダイヤルされた電話番号を、電話の認証と通話ルーティングの目的に合わせて1つの標準 (E.i) 形式に変換する、一連の電話番号の正規化ルールです。 異なる場所からダイヤルされた同じ電話番号は、それぞれのダイヤルプランに基づいて、それぞれの場所に応じて異なる E.i 番号に解決することができます。 エンタープライズ Voip を展開する場合は、その展開の一環としてダイヤルプランを設定する必要があります。また、ダイヤルプランがダイヤルイン会議にも対応していることを確認する必要があります。 エンタープライズ Voip を展開しない場合は、ダイヤルイン会議のダイヤルプランをセットアップする必要があります。  <br/> Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、次のようにダイヤルプランを設定します。  <br/> 1. ダイヤルインアクセス用電話番号のルーティング用に1つ以上のダイヤルプランを作成します。  <br/> 2. 既定のダイヤルプランを各プールに割り当てます。 ダイヤル プランを適用する地理的場所に [**ダイヤルイン会議の地域**] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でダイヤルイン会議を設定する](dial-in-conferencing.md) <br/> [Skype for Business Server でダイヤルプランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**ダイヤル プランが地域に割り当てられていることを確認する** <br/> |**Get-CsDialPlan** コマンドレットと **Set-CsDialPlan** コマンドレットを実行して、すべてのダイヤル プランに地域が割り当てられていることを確認します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でダイヤルイン会議を設定する](dial-in-conferencing.md) <br/> [Skype for Business Server でダイヤルプランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**ダイヤルイン会議をサポートするように会議ポリシーを構成する** <br/> | Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、**会議のポリシー**設定を構成します。 次のことを指定します。 <br/>  PSTN 会議ダイヤルインを有効にするかどうか。 <br/>  ユーザーが匿名参加者を招待できるようにするかどうか。 <br/>  認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server の会議ポリシーを管理する](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**Configure dial-in access numbers** <br/> |Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、ユーザーが電話会議にダイヤルインするためにダイヤルインアクセス番号を設定し、アクセス番号を適切なダイヤルプランに関連付ける地域を指定します。 開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。 [ダイヤルイン会議の設定] ページでは、すべてのアクセス番号を利用できます。  <br/> **注:** ダイヤルインアクセス番号を作成したら、 **CsDialInConferencingAccessNumber**コマンドレットを使用して Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を簡単に識別できるようにすることができます。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でダイヤルプランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Skype for Business Server でダイヤルイン会議アクセス番号を管理する](../../manage/conferencing/access-numbers.md) <br/> [New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**Assign a Line URI to a user account** <br/> |Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、一意の正規化された電話番号としてテレフォニー**回線 URI**を構成します (例: tel: + 14255550200)。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する** <br/> |Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、会議**ピンのポリシー**を表示または変更します。 最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**(オプション) DTMF コマンドの主要なマッピングを変更する** <br/> |**Set-CsDialinConferencingDtmfConfiguration** コマンドレットを使用して、デュアルトーン多重周波数 (DTMF) コマンドで使用される、参加者が会議設定 (ミュートとミュート解除、ロックとロック解除など) を制御するために使用するキーを変更します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server の DTMF コマンドのキーマッピングを管理する](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**(オプション) 電話会議の参加時と退席時のアナウンス動作を変更する** <br/> |**Set-CsDialinConferencingConfiguration** を使用して、参加者が電話会議に参加および退席する際のアナウンス動作を変更します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server で会議への参加とお知らせの脱退を管理する](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**(推奨) 電話会議ディレクトリを構成する** <br/> |**New-CsConferenceDirectory** コマンドレットを使用して、プールに含まれる 999 ユーザーごとに電話会議ディレクトリを 1 つ作成します。 <br/> |RTCUniversalServerAdmins  <br/> |[(Recommended) Create Conference Directories](https://technet.microsoft.com/library/787f4c94-1c96-468a-a74d-e06b7bd4b8a3.aspx) <br/> [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の設定の検証** <br/> |**Get-CsDialinConferencingAccessNumber** コマンドレットを使用して、どのアクセス番号でも使用されていないダイヤルイン会議の地域が設定されたダイヤル プランと、どの地域も割り当てられていないアクセス番号を検索します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[Skype for Business Server でダイヤルイン会議を設定する](dial-in-conferencing.md) <br/> [Skype for Business Server でダイヤルイン会議をテストする](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の検証** <br/> |**Test-CsDialInConferencing** コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business Server でダイヤルイン会議をテストする](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する** <br/> |**CsPinSendCAWelcomeMail**スクリプトを使用して、ユーザーの初期 pin を設定し、初期 Pin とダイヤルイン会議の設定ページへのリンクを含むようこそメールを送信します。 <br/> |RTCUniversalServerAdmins  <br/> |[Skype for Business Server でダイヤルインユーザーにウェルカムメールを送信する](../../manage/conferencing/welcome-emails.md) <br/> |


