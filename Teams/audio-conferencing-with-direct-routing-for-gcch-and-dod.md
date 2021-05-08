---
title: 直接ルーティング、GCCH、DoD を使用した電話会議
author: cichur
ms.author: v-cichur
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
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 管理者は、GCCH および DoD 環境で直接ルーティングを使用して電話会議を使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262622"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High および DoD のダイレクト ルーティングを使用する電話会議

GCC High および DoD の直接ルーティングを使用した電話会議では、参加者は電話デバイスを使用して GCC High または DoD 組織の Teams 会議に参加できます。 会議の参加者は、インターネット接続が制限されている場合や、ユーザーが道路にいて Teams にアクセスできない場合などのシナリオで、電話デバイスを使用して Teams 会議に参加することを好む場合があります。 参加者は、組織のダイヤルイン電話番号にダイヤルインするか、会議を自分の電話デバイスにダイヤルアウトすることで、会議に参加することができます。

GCC High と DoD の直接ルーティングを使用した電話会議では、組織はダイヤルイン電話番号として独自の番号を使用し、電話デバイスへの会議のすべてのダイヤルアウトは、直接ルーティングを介してルーティングされます。 このサービスを有効にするには、直接ルーティングを設定し、ダイヤルイン電話番号として使用できる電話番号を構成する必要があります。 直接ルーティングを使用する要件は、Microsoft がダイヤルイン電話番号を提供する GCC High 以外および DoD 以外の組織に提供される電話会議サービスとは異なります。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>高レベルおよび DoD 向け直接ルーティングを使用GCC電話会議を展開する

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>手順 1: 高いライセンスまたは DoD ライセンスの直接ルーティングGCC電話会議を取得する 

GCC High または DoD で電話会議を使用するには、組織と組織内のユーザーに直接ルーティング ライセンスが割り当てられた電話会議が必要です。 High または DoD の直接ルーティングを使用して電話会議を有効GCCを次に示します。

- GCC[高]: 電話会議 - GCCの高テナント ライセンスと電話会議 - GCCユーザーの高ライセンス。

- DoD: 組織の電話会議 - DoD テナント ライセンスとユーザーの電話会議 - DoD ライセンス。

サービスを有効にするには、テナント ライセンスと少なくとも 1 つのユーザー ライセンスが必要です。 テナント ライセンスのみ、またはユーザー ライセンスでのみサービスを有効にできません。 テナントと組織内のユーザーのサービス ライセンスを取得するには、アカウント チームにお問い合わせください。

> [!IMPORTANT]
> ダイヤルイン電話番号が設定されるまで、ユーザーは直接ルーティングを使用した電話会議を有効にすることはできません。 この記事で説明するダイヤルイン電話番号を設定するまで、GCC High ライセンスまたは DoD ライセンスの直接ルーティングを使用した電話会議をユーザーに割り当てないでお勧めします。  このガイダンスに従う必要が生じない場合は、クライアントのダイヤル パッドTeamsがあります。

### <a name="step-2-set-up-direct-routing"></a>手順 2: ダイレクト ルーティングを設定する

ダイレクト ルーティングを設定するには、次の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md)

- [ダイレクト ルーティングを構成する](direct-routing-configure.md)

> [!NOTE]
> 直接ルーティングを設定する場合は、これら 2 つの記事で説明されている GCC High または DoD 固有の FQDN とポートを使用してください。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>手順 3: ダイヤルイン電話番号を設定する

ダイヤルイン電話番号は、電話会議ブリッジに関連付けられている電話番号です。 これらの番号は、組織内のユーザーがスケジュールした会議に参加するために参加者によって使用されます。 これらの番号は、組織内の会議をスケジュールするユーザーの会議出席招待と[ローカル番号の検索] ページにも含まれます。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>テナントでサービス電話番号を定義する

New-csHybridTelephoneNumber PowerShell コマンドレットを使用して、直接ルーティングを介して電話会議サービスに通話をルーティングするために使用できるテナントのサービス電話番号を定義できます。 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

次に例を示します。
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>組織の電話会議ブリッジにサービス電話番号を割り当てる

Register-csOnlineDialInConferencingServiceNumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービス電話番号を割り当てできます。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Get-CsOnlineDialInConferencingBridge を使用して、電話会議ブリッジの ID を確認できます。 次に例を示します。

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>手順 4: グローバル音声ルーティング ポリシーを定義して、会議からの発信通話のルーティングを有効にする

組織内のユーザーによって開催された会議から PSTN に対して行われた発信通話のルーティングは、組織のグローバル音声ルーティング ポリシーによって定義されます。 組織でグローバル音声ルーティング ポリシーが定義されている場合は、グローバル音声ルーティング ポリシーで、組織内のユーザーが開催した会議から開始されると想定される PSTN への発信通話が許可されます。 組織でグローバル音声ルーティング ポリシーが定義されていない場合は、組織内のユーザーが開催した会議から PSTN への発信通話のルーティングを有効にするポリシーを定義する必要があります。 組織のグローバル音声ルーティング ポリシーは、組織内のユーザーによって PSTN に対して行われた 1 対 1 の呼び出しにも適用されます。 組織内のユーザーに対して PSTN への 1 対 1 の呼び出しが有効になっている場合は、グローバル音声ルーティング ポリシーが、両方の種類の通話に対する組織のニーズを満たします。 

> [!NOTE]
> Location-Based ルーティングは、Microsoft 365 Government Community Cloud (GCC) の高いデプロイまたは DoD デプロイでは使用できません。 電話会議を有効にする場合は、GCC High または DoD 環境の電話会議ユーザーが会議ルーティングに対して有効になっていないことをLocation-Basedしてください。

#### <a name="defining-a-global-voice-routing-policy"></a>グローバル音声ルーティング ポリシーの定義

グローバル音声ルーティング ポリシーは、PSTN の使用法、音声ルート、音声ルーティング ポリシーを定義し、新しい音声ルーティング ポリシーを組織のグローバル音声ルーティング ポリシーとして割り当てる方法で定義できます。

次の手順では、組織に新しいグローバル音声ルーティング ポリシーを定義する方法について説明します。 組織で既に音声ルーティング ポリシーが定義されている場合は、次の構成が組織の既存の音声ルーティング ポリシーと競合されていないことを確認します。

Skype for Business Online のリモート PowerShell セッションで新しい PSTN 使用量を作成するには、次のコマンドを使用します。

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

詳細については [、Set-CsOnlinePstnUsage に関するページを参照してください](/powershell/module/skype/set-csonlinepstnusage)。

新しい音声ルートを作成するには、次のコマンドを使用します。

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

組織の新しい音声ルートを定義する場合は、直接ルーティングの構成中に組織に対して定義されている PSTN オンライン PSTN ゲートウェイの 1 つ以上を指定してください。 

番号パターンは、呼び出しの宛先電話番号に基づいて、指定されたゲートウェイのリストを介してルーティングされる呼び出しを指定します。 上記の例では、世界中の任意の宛先への呼び出しが音声ルートと一致します。 組織内のユーザーの会議からダイヤルできる電話番号を制限する場合は、音声ルートが許可されている宛先の番号パターンにのみ一致する番号パターンを変更できます。 特定の通話の宛先電話番号の番号パターンに一致する音声ルートがない場合、通話はルーティングされません。

詳細については [、New-CsOnlineVoiceRoute に関するページを参照してください](/powershell/module/skype/new-csonlinevoiceroute)。

新しい音声ルーティング ポリシーを作成するには、次のコマンドを使用します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

音声ルーティング ポリシーで複数の PSTN 使用法が定義されている場合は、定義された順序で評価されます。 PSTN の使用に関連付けられている音声ルートの番号パターンの観点から、PSTN の使用を最も一般的な順に定義してください。 たとえば、PSTN の使用が米国への通話をルーティングするために定義され、別の PSTN 使用法が世界の他の場所に通話をルーティングするために定義されている場合、通話を世界中の他の場所にルーティングするために PSTN の使用の前に、米国への通話の PSTN 使用法が音声ルーティング ポリシーに一覧表示される必要があります。

詳細については [、New-CsOnlineVoiceRoutingPolicy に関するページを参照してください](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

組織のグローバル音声ルーティング ポリシーに新しい音声ルートを割り当てるには、次のコマンドを使用します。

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

詳細については [、Grant-CsOnlineVoiceRoutingPolicy に関するページを参照してください](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

グローバル音声ルーティング ポリシーを定義すると、組織内のユーザーによって開催された会議から発信された通話は、グローバル音声ルーティング ポリシーの PSTN 使用法に関連付けられた音声ルートに対して評価されます。 発信通話は、ダイヤルされた電話番号の番号パターンに一致する最初の音声ルートに従ってルーティングされます。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>手順 5: 高いライセンスまたは DoD ライセンスの直接ルーティングGCC電話会議をユーザーに割り当てる

GCC High または DoD ライセンスの直接ルーティングによる電話会議をユーザーに割り当てるには、「ユーザーにライセンスを割り当てる[」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>手順 6: (省略可能) [電話会議番号] の一覧を表示Teams

組織の電話会議番号の一覧を表示するには、「電話会議番号の一覧を表示する」を参照[Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>手順 7: (省略可能) 組織の電話会議ダイヤルイン番号の自動応答言語を設定する

組織の電話会議ダイヤルイン番号の言語を変更するには、「電話会議の自動応答言語を設定する」を参照[Microsoft Teams。](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>手順 8: (省略可能) 組織の電話会議ブリッジの設定を変更する

組織の電話会議ブリッジの設定を変更するには、「電話会議ブリッジの設定を変更 [する」を参照してください](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>手順 9: (省略可能) 組織内のユーザーの会議出席招待に含まれる電話番号を設定する

ユーザーの会議出席招待に含まれる電話番号のセットを組織に変更するには、「Microsoft Teams で招待に含まれる電話番号を設定する」[を参照してください](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>高レベルと DoD の直接ルーティングを使用した電話会議GCC機能

[高] と [DoD] の直接ルーティングを使用した電話会議ではサポートされていない電話会議GCC次に示します。

- 名前の記録を使用して通知を開始および終了します。 直接ルーティングを使用した電話会議の場合、入退出通知は会議でトーンとして再生されます。

- 電話会議の発信通話制限ポリシー。 発信通話を制限するユーザー レベルの制御は、ダイレクト ルーティングを介してルーティングされたダイヤルアウト通話の会議には適用されません。

- 会議固有の開催者の無料電話番号の使用を無効にします。 組織の会議に参加するために無料電話番号の使用を制限するユーザー レベルの制御は、ダイレクト ルーティングを介してルーティングされた通話には適用されません。

- 設定が変更された場合にユーザーに通知メールを送信する。 電話会議通知メールは、高レベルと DoD の直接ルーティングを使用した電話会議GCCサポートされていません。