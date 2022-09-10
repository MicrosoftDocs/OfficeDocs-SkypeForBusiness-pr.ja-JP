---
title: 直接ルーティング、GCCH、DoD を使用した電話会議
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 管理は、GCCH および DoD 環境で電話会議とダイレクト ルーティングを使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641778"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High および DoD のダイレクト ルーティングを使用する電話会議

GCC High と DoD のダイレクト ルーティングを使用した電話会議では、参加者は電話デバイスを使用して GCC High または DoD 組織内の Teams 会議に参加できます。 会議参加者は、インターネット接続が制限されている場合や、ユーザーが外出先で Teams にアクセスできない場合など、電話デバイスを使用して Teams 会議に参加することをお勧めします。 参加者は、組織のダイヤルイン電話番号にダイヤルインするか、会議を自分の電話デバイスにダイヤルアウトすることで、会議に参加することを選択できます。

GCC High と DoD 用のダイレクト ルーティングを使用した電話会議では、組織はダイヤルイン電話番号として独自の番号を使用し、電話デバイスへの会議のすべてのダイヤルアウトはダイレクト ルーティング経由でルーティングされます。 このサービスを有効にするには、組織はダイレクト ルーティングを設定し、ダイヤルイン電話番号として使用できる電話番号を構成する必要があります。 ダイレクト ルーティングを使用する要件は、ダイヤルイン電話番号が Microsoft によって提供される GCC High および DoD 以外の組織に提供される電話会議サービスとは異なります。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High および DoD 用のダイレクト ルーティングを使用して電話会議を展開する

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>手順 1: GCC High または DoD ライセンスのダイレクト ルーティングを使用して電話会議を取得する

GCC High または DoD で電話会議を使用するには、組織と組織内のユーザーに、ダイレクト ルーティング ライセンスが割り当てられた電話会議が必要です。 GCC High または DoD のダイレクト ルーティングを使用して電話会議を有効にするために必要なライセンスを次に示します。

- GCC High: 電話会議 - 組織の GCC High Tenant ライセンスと電話会議 - ユーザー用の GCC High ライセンス。

- DoD: 組織の電話会議 - DoD テナント ライセンスと電話会議 - ユーザーの DoD ライセンス。

サービスを有効にするには、テナント ライセンスと少なくとも 1 つのユーザー ライセンスが必要です。 テナント ライセンスのみ、またはユーザー ライセンスのみでサービスを有効にすることはできません。 テナントと組織内のユーザーのサービス ライセンスを取得するには、アカウント チームに問い合わせてください。

> [!IMPORTANT]
> ダイヤルイン電話番号が設定されるまで、ユーザーは直接ルーティングを使用して電話会議を有効にすることはできません。 この記事で説明するようにダイヤルイン電話番号を設定するまで、GCC High または DoD ライセンスのダイレクト ルーティングを使用して電話会議をユーザーに割り当てないことをお勧めします。  このガイダンスに従わないと、Teams クライアントでダイヤル パッドが完全に見つからない可能性があります。

### <a name="step-2-set-up-direct-routing"></a>手順 2: ダイレクト ルーティングを設定する

ダイレクト ルーティングを設定するには、次の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md)

- [ダイレクト ルーティングを構成する](direct-routing-configure.md)

> [!NOTE]
> ダイレクト ルーティングを設定するときは、これら 2 つの記事で説明されている GCC High または DoD 固有の FQDN とポートを必ず使用してください。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>手順 3: ダイヤルイン電話番号を設定する

ダイヤルイン電話番号は、電話会議ブリッジに関連付けられている電話番号です。 これらの番号は、組織内のユーザーによってスケジュールされた会議に参加するために参加者によって使用されます。 これらの番号は、組織内で会議をスケジュールするユーザーの会議への招待や[ローカル番号の検索] ページにも含まれます。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>テナントでサービス電話番号を定義する

New-csHybridTelephoneNumber PowerShell コマンドレットを使用して、直接ルーティング経由で電話会議サービスに通話をルーティングするために使用できるサービス電話番号をテナント内で定義できます。

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

次に例を示します。

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>組織の電話会議ブリッジにサービス電話番号を割り当てる

Register-csOnlineDialInConferencingServiceNumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービス電話番号を割り当てることができます。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Get-CsOnlineDialInConferencingBridge を使用して、電話会議ブリッジの ID を確認できます。 次に例を示します。

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>手順 4: 会議からの発信通話のルーティングを有効にするグローバル音声ルーティング ポリシーを定義する

組織内のユーザーによって組織された会議から PSTN に対して行われる発信通話のルーティングは、組織のグローバル音声ルーティング ポリシーによって定義されます。 組織にグローバル音声ルーティング ポリシーが定義されている場合は、グローバル音声ルーティング ポリシーで、組織内のユーザーが開催した会議から開始される予定の PSTN への発信通話が許可されていることを確認します。 組織にグローバル音声ルーティング ポリシーが定義されていない場合は、組織内のユーザーによって組織された会議から PSTN への発信通話のルーティングを有効にする 1 つを定義する必要があります。 組織のグローバル音声ルーティング ポリシーは、組織内のユーザーによって PSTN に対して行われた 1 対 1 の通話にも適用されることに注意してください。 組織内のユーザーに対して PSTN への 1 対 1 の通話が有効になっている場合は、グローバル音声ルーティング ポリシーが両方の種類の通話に対する組織のニーズを満たしていることを確認します。

> [!NOTE]
> Location-Based ルーティングは、Microsoft 365 Government Community Cloud (GCC) High または DoD の展開では使用できません。 電話会議を有効にする場合は、GCC High または DoD 環境の電話会議ユーザーがルーティングLocation-Based有効になっていないことを確認します。

#### <a name="defining-a-global-voice-routing-policy"></a>グローバル音声ルーティング ポリシーの定義

グローバル音声ルーティング ポリシーは、PSTN 使用法、音声ルート、音声ルーティング ポリシーを定義し、組織のグローバル音声ルーティング ポリシーとして新しい音声ルーティング ポリシーを割り当てることで定義できます。

次の手順では、組織に新しいグローバル音声ルーティング ポリシーを定義する方法について説明します。 組織に既に音声ルーティング ポリシーが定義されている場合は、次の構成が組織の既存の音声ルーティング ポリシーと競合しないことを確認します。

Teams のリモート PowerShell セッションで新しい PSTN 使用法を作成するには、次のコマンドを使用します。

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

詳細については、「 [Set-CsOnlinePstnUsage」を](/powershell/module/skype/set-csonlinepstnusage)参照してください。

新しい音声ルートを作成するには、次のコマンドを使用します。

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

組織の新しい音声ルートを定義する場合は、直接ルーティングの構成中に組織に対して定義された PSTN オンライン PSTN ゲートウェイの 1 つまたは複数を指定します。

番号パターンは、呼び出し先の電話番号に基づいて、指定されたゲートウェイの一覧を経由してルーティングされる呼び出しを指定します。 上の例では、世界中の宛先への呼び出しが音声ルートと一致します。 組織内のユーザーの会議からダイヤルできる電話番号を制限する場合は、音声ルートが許可されている宛先の番号パターンのみに一致するように番号パターンを変更できます。 特定の通話の宛先電話番号の番号パターンに一致する音声ルートがない場合、通話はルーティングされないことに注意してください。

詳細については、「 [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute)」を参照してください。

新しい音声ルーティング ポリシーを作成するには、次のコマンドを使用します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

音声ルーティング ポリシーで複数の PSTN 使用法が定義されている場合は、それらが定義されている順序で評価されます。 PSTN 使用法は、PSTN 使用法に関連付けられている音声ルートの番号パターンの観点から、より一般的な用途に最も固有の順序で定義することをお勧めします。 たとえば、米国に通話をルーティングするために PSTN 使用法が定義されており、通話を世界の他の場所にルーティングするために別の PSTN 使用法が定義されている場合、通話を世界の他の場所にルーティングするには、PSTN の使用の前に音声ルーティング ポリシーに米国への通話に対する PSTN 使用法を一覧表示する必要があります。

詳細については、「 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)」を参照してください。

組織のグローバル音声ルーティング ポリシーに新しい音声ルートを割り当てるには、次のコマンドを使用します。

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

詳細については、「 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)」を参照してください。

グローバル音声ルーティング ポリシーが定義されると、組織内のユーザーによって組織された会議から発信された通話はすべて、グローバル音声ルーティング ポリシーの PSTN 使用法に関連付けられている音声ルートに対して評価されます。 発信通話は、ダイヤルされた電話番号の番号パターンに一致する最初の音声ルートに従ってルーティングされます。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>手順 5: GCC High または DoD ライセンスのダイレクト ルーティングを使用して電話会議をユーザーに割り当てる

GCC High または DoD ライセンスのダイレクト ルーティングを使用して電話会議をユーザーに割り当てるには、「ユーザー [にライセンスを割り当てる」を](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>手順 6: (省略可能) Teams の電話会議番号の一覧を表示する

組織の電話会議番号の一覧を表示するには、 [Microsoft Teams の電話会議番号の一覧を表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)に移動します。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>手順 7: (省略可能) 組織の電話会議ダイヤルイン番号の自動応答言語を設定する

組織の電話会議ダイヤルイン番号の言語を変更するには、「 [Microsoft Teams で電話会議の自動応答言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)」を参照してください。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>手順 8: (省略可能) 組織の電話会議ブリッジの設定を変更する

組織の電話会議ブリッジの設定を変更するには、「 [電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>手順 9: (省略可能) 組織内のユーザーの会議出席依頼に含まれる電話番号を設定する

ユーザーの会議出席依頼に含まれる電話番号のセットを組織に変更するには、「 [Microsoft Teams の招待に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High および DoD 用のダイレクト ルーティングを使用した電話会議ではサポートされていない電話会議機能

GCC High および DoD のダイレクト ルーティングを使用した電話会議ではサポートされていない電話会議機能を次に示します。

- 名前の記録を使用した入退室通知。 直接ルーティングを使用した電話会議の場合、会議では入退室通知がトーンとして再生されます。

- 会議固有の開催者のフリーダイヤル番号の使用を無効にします。 組織の会議に参加するためのフリーダイヤル番号の使用を制限するユーザー レベルの制御は、ダイレクト ルーティング経由でルーティングされる通話には適用されません。

- 設定が変更されたときにユーザーに通知メールを送信する。 電話会議通知電子メールは、GCC High と DoD のダイレクト ルーティングを使用した電話会議ではサポートされていません。
