---
title: Skype で会議をビジネスのサーバーを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '概要: ビジネス サーバー用 Skype で会議を展開する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: e004afdc420bcd99679e20c29bf6ba7efc7f735f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263824"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>Skype で会議をビジネスのサーバーを展開します。

**の概要:** ビジネス サーバー用 Skype で会議を展開する方法の詳細については、このトピックを参照してください。

Skype ビジネス サーバーで利用可能なは会議の 4 つの種類があります: web 会議、オーディオおよびビデオ (A/V) 会議、ダイヤルイン会議、およびインスタント メッセージ (IM) 会議。 すべての種類の会議を有効にするか、お客様のニーズに応じて、1 つだけの種類を使用することができます。

Skype ビジネス サーバーを配置すると、IM 会議の機能が自動的に展開します。 トポロジ ビルダーを使用して新しいトポロジを作成および公開するときに、次のチェックリストで説明するように、Web、A/V、ダイヤルインの各会議を展開するかどうかを指定します。

- [Deployment checklist for web and audio/video conferencing](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [ダイヤルイン会議の展開に関するフローチャートとチェックリスト](deploy-conferencing.md#BKMK_DialinConferencing)

会議を展開する前に次の計画のトピックをお読みください。

- [ビジネス サーバーに、Skype で会議を計画します。](../../plan-your-deployment/conferencing/conferencing.md)

- [ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [Skype のビジネス サーバーの会議トポロジを計画します。](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [ビジネス サーバーの Skype では、ダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [ビジネス サーバーの Skype での大規模な会議の計画](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web 会議と音声ビデオ会議の展開チェックリスト
<a name="BKMK_ChecklistWebConferencing"> </a>

次の表に、既存のトポロジに Web 会議と音声ビデオ会議を展開するために必要なステップの概要を示します。 関連する計画および手順に関するドキュメントへのリンクも掲載します。

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |会議は、フロント エンド プールのフロント エンド サーバーと Standard Edition サーバーで実行されます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。  <br/> Web カンファレンスを有効にする場合は、Skype のビジネス サーバーは、Office アプリケーション、Web サーバーの共有と PowerPoint プレゼンテーションのレンダリングを処理するために使用すると通信できることを確認する必要があります。  <br/> Web 会議に関して、ファイル ストアとして使用するファイル共有も指定する必要があります。  <br/> Skype for Business クライアントの外部ユーザーが、会議に参加できるようにする必要がありますか。参加を許可する場合は、エッジ サーバーを展開する必要があります。  <br/> |ローカル Administrators グループのメンバーであるドメイン ユーザー  <br/> | [ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md) <br> [Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [ビジネス サーバー用の Skype では、Office Web アプリケーション サーバーとの統合を構成します。](office-web-app-server.md) <br/> [Skype のビジネス サーバーのファイル共有を作成します。](../../deploy/install/create-a-file-share.md) <br/> [Skype for Business Server 2015 でのエッジ サーバーの展開の計画](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [Skype for Business Server 2015 でのエッジ サーバーの展開](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**会議をサポートするために適切な内部トポロジの作成** <br/> |会議をトポロジに追加し、トポロジを公開し、トポロジ ビルダーを実行する必要があります。  <br/> |トポロジを定義するには、ローカル Users グループのメンバーであるアカウント  <br/> ビジネス サーバーのファイル ストアの Skype に使用するファイル共有のトポロジでは、RTCUniversalServerAdmins グループ、Domain Admins グループのメンバーであるし、フル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウントを発行する (ようにトポロジビルダーでは、必要な Dacl を構成することができます)  <br/> |[作成し、Skype のビジネス サーバーの新しいトポロジを公開](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**会議ポリシーと構成設定の構成** <br/> |会議ポリシーおよび構成設定を構成するのには、ビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype の Skype を使用します。  <br/> |RTCUniversalServerAdmins グループ (Windows PowerShell の場合のみ) または CSAdministrator の役割に割り当てるユーザー  <br/> |[Skype での会議のポリシーを管理するビジネス サーバー](../../manage/conferencing/conferencing-policies.md) <br/> [管理会議の Skype ビジネス サーバーの構成設定](../../manage/conferencing/meeting-configuration-settings.md) <br/> [CsConferencingPolicy で新しい](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [新しい-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [セット CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [新しい-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [セット CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>ダイヤルイン会議の展開に関するフローチャートとチェックリスト
<a name="BKMK_DialinConferencing"> </a>

 ダイヤルイン会議を使用すると、ユーザーが公衆交換電話網 (PSTN) を使用して、音声ビデオ会議にダイヤルインできます。

エンタープライズ VoIP のダイヤルイン会議に必要なコンポーネントのいくつか使用されます。 など、エンタープライズ VoIP を展開する場合、仲介サーバーと PSTN ゲートウェイ - ダイヤルイン会議に必要なコンポーネントも配置する必要があります。 ダイヤルイン会議を展開する方法で、エンタープライズ VoIP ソリューションも展開するかどうか、によって異なります。

このダイヤルイン会議のフローチャートでは、エンタープライズ VoIP ソリューションも展開するかどうかに応じて、従う必要のある手順を示します。 フローチャートの後の表では、ダイヤルイン会議を展開する際に必須の手順と推奨される手順の概要を示します。 関連する計画および手順に関するドキュメントへのリンクも掲載します。 完全なエンタープライズ VoIP ソリューションの計画に関する詳細については、 [Skype のビジネス サーバーでエンタープライズ VoIP ソリューションを計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)を参照してください。

**ダイヤルイン会議の展開フローチャート**

![ダイヤル会議のフロー チャートを展開する](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**ダイヤルイン会議の展開チェックリスト**

|**段階**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> | 会議は、フロント エンド プールのフロント エンド サーバーと Standard Edition サーバーで実行されます。 フロント エンド サーバーのサーバー要件と環境要件を参照してください。 <br/>  ダイヤルイン会議を構成する前に次の項目がインストールされていることを確認する必要があります。 <br/>  仲介サーバー <br/>  PSTN ゲートウェイ <br/>  統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます) <br/>  会議アテンダント アプリケーション <br/>  会議アナウンス アプリケーション <br/> |ローカル Administrators グループのメンバーであるドメイン ユーザー  <br/> |[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [ビジネス サーバーの Skype では、ダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [Skype ビジネス サーバー用の仲介サーバーのコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [ビジネス サーバーのトポロジ ビルダーで Skype に仲介サーバーを展開します。](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [ビジネス サーバーの Skype でトポロジ ビルダーでゲートウェイを定義します。](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**仲介サーバーと PSTN ゲートウェイを含む、会議ワークロードを含むトポロジを作成し、フロント エンド プールまたは Standard Edition サーバーを展開します。** <br/> |1. トポロジを構成するのにはトポロジ ビルダーを実行します。 トポロジの構成時に、ダイヤルイン会議オプションを選択します。  <br/> 2. トポロジを公開し、フロント エンド プールまたは Standard Edition サーバーを展開します。  <br/> 3. 必要に応じて、スタンドアロンの仲介サーバーを作成し、PSTN ゲートウェイに関連付けます。  <br/> **注:** この手順は、エンタープライズ VoIP を展開しないようにし、エンタープライズ エディションのフロント エンド サーバーまたは Standard Edition サーバーを仲介サーバーを連結しない場合にのみ必要です。 エンタープライズ VoIP を展開する場合は、インストールし、エンタープライズ VoIP 展開の一部として仲介サーバーと PSTN ゲートウェイを構成します。 仲介サーバーを連結する場合は、インストールし、仲介サーバーをフロント エンド プールまたは Standard Edition サーバーの展開の一部として構成します。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> Administrator  <br/> |[作成し、Skype のビジネス サーバーの新しいトポロジを公開](../../deploy/install/create-and-publish-new-topology.md) <br/> [ビジネス サーバーのトポロジ ビルダーで Skype に仲介サーバーを展開します。](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [ビジネス サーバーの Skype でトポロジ ビルダーでゲートウェイを定義します。](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**ダイヤル プランを構成する** <br/> |ダイヤル プランは、電話の承認および通話のルーティングのために 1 つの標準 (E.164) 形式に特定の場所からダイヤルする電話番号を変換する電話番号の正規化ルールのセットです。 同じ電話番号が別の場所からのダイヤル、それぞれのダイヤル プランに基づく解決には、それぞれの場所に応じて、別の E.164 番号します。 エンタープライズ VoIP を展開する場合は、ダイヤル プランをその展開の一部として設定することを確認する必要がありますダイヤル プランには、ダイヤルイン会議も対応します。 エンタープライズ VoIP を展開しない場合は、ダイヤルイン会議のダイヤル プランを設定する必要があります。  <br/> ビジネス サーバーのコントロール パネルを使用して Skype または Skype ビジネス サーバーの管理シェルを設定するには、ダイヤル プランを次のように。  <br/> 1. ルーティングのダイヤルインのアクセス電話番号を 1 つまたは複数のダイヤル プランを作成します。  <br/> 2. 各プールに既定のダイヤル プランを割り当てます。 ダイヤル プランを適用する地理的場所に [**ダイヤルイン会議の地域**] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype のビジネス サーバーのダイヤルイン会議を構成します。](dial-in-conferencing.md) <br/> [作成またはビジネス サーバーの Skype のダイヤル プランを変更します。](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [新しい-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**ダイヤル プランが地域に割り当てられていることを確認する** <br/> |**Get-CsDialPlan** コマンドレットと **Set-CsDialPlan** コマンドレットを実行して、すべてのダイヤル プランに地域が割り当てられていることを確認します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype のビジネス サーバーのダイヤルイン会議を構成します。](dial-in-conferencing.md) <br/> [作成またはビジネス サーバーの Skype のダイヤル プランを変更します。](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [セット CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**ダイヤルイン会議をサポートするように会議ポリシーを構成する** <br/> | **会議ポリシー**設定を構成するのには、ビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype の Skype を使用します。 次のことを指定します。 <br/>  PSTN 会議ダイヤルインを有効にするかどうか。 <br/>  ユーザーが匿名参加者を招待できるようにするかどうか。 <br/>  認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype での会議のポリシーを管理するビジネス サーバー](../../manage/conferencing/conferencing-policies.md) <br/> [CsConferencingPolicy で新しい](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**ダイヤルイン アクセス番号を構成する** <br/> |ビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype の Skype を使用して、会議にダイヤルインするユーザーを呼び出すダイヤルイン アクセス番号を設定し、アクセス数を適切なダイヤル プランに関連付ける領域を指定します。 開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。 [ダイヤルイン会議の設定] ページで、すべてのアクセス番号を利用できます。  <br/> **注:** ダイヤルイン アクセス番号を作成した後、ユーザーが正しいアクセス番号を簡単に識別できるように、Active Directory 連絡先オブジェクトの表示名を変更するのには、**セット CsDialInConferencingAccessNumber**コマンドレットを使用することができます。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[作成またはビジネス サーバーの Skype のダイヤル プランを変更します。](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Skype でダイヤルイン会議のアクセス番号をビジネスのサーバーの管理します。](../../manage/conferencing/access-numbers.md) <br/> [新しい-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [セット CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**Assign a Line URI to a user account** <br/> |として一意のテレフォニー**回線 URI**を構成するには、ビジネス サーバーのコントロール パネルを使用して Skype または Skype ビジネス サーバー管理シェルの電話番号を正規化 (たとえば、tel: +14255550200)。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する** <br/> |会議**PIN ポリシー**の変更を表示またはビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype の Skype を使用します。 最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ビジネス サーバーの Skype では、ダイヤルイン会議の暗証番号 (pin) ポリシーを管理します。](../../manage/conferencing/pin-policies.md) <br/> [Get CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [セット CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**(オプション) DTMF コマンドの主要なマッピングを変更する** <br/> |**Set-CsDialinConferencingDtmfConfiguration** コマンドレットを使用して、デュアルトーン多重周波数 (DTMF) コマンドで使用される、参加者が会議設定 (ミュートとミュート解除、ロックとロック解除など) を制御するために使用するキーを変更します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ビジネス サーバー Skype の DTMF コマンドのキー マッピングを管理します。](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [セット CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**(オプション) 電話会議の参加時と退席時のアナウンス動作を変更する** <br/> |**Set-CsDialinConferencingConfiguration** を使用して、参加者が電話会議に参加および退席する際のアナウンス動作を変更します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[会議の参加を管理し、お知らせの Skype ビジネス サーバーのままに](../../manage/conferencing/join-and-leave-announcements.md) <br/> [セット CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**(推奨) 電話会議ディレクトリを構成する** <br/> |**New-CsConferenceDirectory** コマンドレットを使用して、プールに含まれる 999 ユーザーごとに電話会議ディレクトリを 1 つ作成します。 <br/> |RTCUniversalServerAdmins  <br/> |[(推奨) 会議ディレクトリを作成する](https://technet.microsoft.com/library/787f4c94-1c96-468a-a74d-e06b7bd4b8a3.aspx) <br/> [新しい-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の設定の検証** <br/> |**Get-CsDialinConferencingAccessNumber** コマンドレットを使用して、どのアクセス番号でも使用されていないダイヤルイン会議の地域が設定されたダイヤル プランと、どの地域も割り当てられていないアクセス番号を検索します。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[Skype のビジネス サーバーのダイヤルイン会議を構成します。](dial-in-conferencing.md) <br/> [Skype のビジネス サーバーのダイヤルイン会議をテストします。](../../manage/conferencing/tests.md) <br/> [Get CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(オプション) ダイヤルイン会議の検証** <br/> |**Test-CsDialInConferencing** コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype のビジネス サーバーのダイヤルイン会議をテストします。](../../manage/conferencing/tests.md) <br/> [テスト CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する** <br/> |**セット CsPinSendCAWelcomeMail**スクリプトを使用して、ユーザーの最初の Pin を設定し、初期の暗証番号 (pin) およびダイヤルイン会議の設定のページへのリンクを含むウェルカム電子メールを送信します。 <br/> |RTCUniversalServerAdmins  <br/> |[ダイヤルに登録完了メールを送信するビジネス サーバーの Skype のユーザー](../../manage/conferencing/welcome-emails.md) <br/> |


