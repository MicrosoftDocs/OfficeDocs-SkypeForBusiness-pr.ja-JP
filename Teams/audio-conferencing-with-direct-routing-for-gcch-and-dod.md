---
title: Direct Routing、GCCH、DoD を搭載した電話会議
author: LanaChin
ms.author: v-lanac
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
description: 管理者は、GCCH および DoD 環境で直接ルーティングを使用して電話会議を使用する方法について知ることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262494"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High および DoD のダイレクト ルーティングを使用する電話会議

GCC 高と DoD で直接ルーティングを使用した電話会議により、参加者はスマートフォンデバイスを使って、GCC 高または DoD 組織の Teams 会議に参加することができます。 会議の参加者は、インターネット接続が制限されている場合や、ユーザーが外出中で、Teams へのアクセス権を持っていない場合などのシナリオで、電話デバイスを使って Teams 会議に参加することができます。 参加者は、組織のダイヤルイン電話番号にダイヤルインするか、会議を電話デバイスにダイヤルアウトすることで、会議に参加することを選ぶことができます。

スマートフォン高と DoD の直行ルーティングを使用した電話会議を使用する場合、組織では、独自の番号をダイヤルイン電話番号として使用し、電話デバイスへの会議のすべてのダイヤルアウトは、直接ルーティングを介してルーティングされます。 このサービスを有効にするには、組織はダイレクトルーティングを設定し、ダイヤルイン電話番号として使用できる電話番号を構成する必要があります。 直接ルーティングを使用するための要件は、スマートフォン以外の組織で、Microsoft がダイヤルイン電話番号を提供している非 GCC 高および DoD 以外の組織で提供されている電話会議サービスとは異なります。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High and DoD のダイレクトルーティングを使用して電話会議を展開する

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>手順 1: GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議を取得する 

GCC 高または DoD で電話会議を使用するには、組織内の組織とユーザーが、ダイレクトルーティングライセンスを割り当てられた電話会議を利用している必要があります。 GCC 高または DoD のダイレクトルーティングを使用して電話会議を有効にするために必要なライセンスを次に示します。

- GCC High: 電話会議-組織および電話会議用の GCC 高テナントライセンス-ユーザー向けのスマートな高ライセンス。

- DoD: 組織および電話会議のための電話会議 (DoD テナントライセンス)-ユーザー向けの DoD ライセンス。

サービスを有効にするには、テナントライセンスと少なくとも1つのユーザーライセンスが必要です。 テナントライセンスのみで、またはユーザーライセンスのみを使用してサービスを有効にすることはできません。 テナントと組織内のユーザーのサービスライセンスを取得するには、アカウントチームにお問い合わせください。

> [!IMPORTANT]
> ダイヤルイン電話番号が設定されるまで、直接ルーティングを使用して電話会議のユーザーを有効にすることはできません。 この記事で説明されているようにダイヤルイン電話番号を設定しない限り、スマートフォンの高または米国のライセンスを直接ルーティングする電話会議をユーザーに割り当てることは禁じられています。

### <a name="step-2-set-up-direct-routing"></a>手順 2: ダイレクトルーティングを設定する

直接ルーティングを設定するには、次の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md)

- [ダイレクト ルーティングを構成する](direct-routing-configure.md)

> [!NOTE]
> 直接ルーティングを設定する場合は、以下の2つの記事で説明されている GCC 高または DoD 固有の Fqdn とポートを使用してください。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>手順 3: ダイヤルイン電話番号を設定する

ダイヤルイン電話番号は、電話会議ブリッジに関連付けられている電話番号です。 これらの番号は、組織内のユーザーによってスケジュールされた会議に参加するために参加者が使用します。 この番号は、組織で会議をスケジュールするユーザーの会議出席依頼にも含まれています。また、[電話番号の検索] ページでも利用できます。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>テナントのサービス電話番号を定義する

CsHybridTelephoneNumber PowerShell コマンドレットを使用して、テナント内のサービス電話番号を定義することができます。これにより、直接ルーティングを使用して電話会議サービスへの呼び出しをルーティングすることができます。 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

次に例を示します。
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>サービスの電話番号を組織の電話会議ブリッジに割り当てる

Set-csonlinedialinconferencingservicenumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービスの電話番号を割り当てることができます。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Get-csonlinedialinconferencingbridge を使用して、電話会議ブリッジの ID を確認できます。 次に例を示します。

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>手順 4: グローバルボイスルーティングポリシーを定義して、会議からの発信通話のルーティングを有効にする

組織内のユーザーによって開催された会議からの PSTN に対する発信通話のルーティングは、組織のグローバルボイスルーティングポリシーによって定義されます。 グローバルボイスルーティングポリシーが定義されている組織の場合は、グローバルボイスルーティングポリシーによって、組織内のユーザーによって開催される会議から開始される可能性がある PSTN への発信通話が許可されていることを確認してください。 組織にグローバルボイスルーティングポリシーが定義されていない場合は、組織内のユーザーによって開催された会議からの、PSTN への発信通話のルーティングを有効にするように定義する必要があります。 組織のグローバルボイスルーティングポリシーは、組織内のユーザーによって PSTN に行われる1対1の通話にも適用されることに注意してください。 組織内のユーザーに対して、PSTN への1対1の通話が有効になっている場合は、グローバルボイスルーティングポリシーが両方の種類の通話に対して組織のニーズを満たしていることを確認してください。 

> [!NOTE]
> 位置情報に基づくルーティングは、Microsoft 365 Government Community Cloud (GCC) 高または DoD の展開では使用できません。 電話会議を有効にする場合は、場所に基づくルーティングで、GCC 高または DoD 環境で電話会議ユーザーが有効になっていないことを確認してください。

#### <a name="defining-a-global-voice-routing-policy"></a>グローバルボイスルーティングポリシーを定義する

グローバルボイスルーティングポリシーを定義するには、PSTN 使用状況、音声ルート、音声ルーティングポリシーを定義し、新しいボイスルーティングポリシーを組織のグローバルボイスルーティングポリシーとして割り当てます。

次の手順では、1つの組織に対して新しいグローバルボイスルーティングポリシーを定義する方法について説明します。 組織に既に音声ルーティングポリシーが定義されている場合は、次の構成が組織の既存の音声ルーティングポリシーと競合していないことを確認します。

Skype for Business Online のリモート PowerShell セッションで新しい PSTN 使用量を作成するには、次のコマンドを使用します。

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

詳細については、「 [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)」を参照してください。

新しいボイスルートを作成するには、次のコマンドを使用します。

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

組織の新しいボイスルートを定義する場合は、直接ルーティングの構成時に組織に対して定義されている PSTN オンライン PSTN ゲートウェイの1つまたは複数を指定してください。 

番号パターンでは、通話の発信先電話番号に基づいて、指定したゲートウェイの一覧を通じてルーティングされる通話を指定します。 上記の例では、世界中のどこにでも通話を発信できます。 組織内のユーザーの会議からダイヤルできる電話番号を制限する場合は、番号パターンを変更して、音声ルートが許可されている送信先の番号パターンだけに一致するようにすることができます。 指定した通話の発信先電話番号の番号パターンと一致するボイスルートがない場合、通話はルーティングされません。

詳細については、「 [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)」を参照してください。

新しいボイスルーティングポリシーを作成するには、次のコマンドを使用します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

ボイスルーティングポリシーで複数の PSTN の使用が定義されている場合は、それらのユーザーが定義された順序で評価されます。 Pstn の利用状況に関連付けられているボイスルートの番号パターンについては、最も限定的な順番で PSTN を定義することをお勧めします。 たとえば、PSTN の使用状況が、米国への通話をルーティングするように定義されていて、別の PSTN 利用状況が世界中の他の場所への通話をルーティングするように定義されている場合、世界中の他の場所への通話をルーティングするために、pstn 使用の前にボイスルーティングポリシーに含まれている必要

詳細については、「 [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)」を参照してください。

組織のグローバルボイスルーティングポリシーに新しいボイスルートを割り当てるには、次のコマンドを使用します。

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

詳細については、「 [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)」を参照してください。

グローバルボイスルーティングポリシーを定義すると、組織内のユーザーによって開催された会議から発信されたすべての発信通話は、グローバルボイスルーティングポリシーの PSTN 使用状況に関連付けられているボイスルートと照らし合わせて評価されます。 発信通話は、ダイヤルした電話番号の番号パターンと一致する最初のボイスルートに従ってルーティングされます。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>手順 5: ユーザーに GCC の高または DoD ライセンスのダイレクトルーティングを使用して電話会議を割り当てる

GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議をユーザーに割り当てる方法については、「 [ユーザーへのライセンスの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>手順 6: (オプション) Teams で電話会議番号のリストを表示する

組織の電話会議番号の一覧を表示するには、 [「Microsoft Teams で電話会議番号のリストを表示する」](see-a-list-of-audio-conferencing-numbers-in-teams.md)に進みます。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>手順 7: (省略可能) 組織の電話会議のダイヤルイン番号用に自動応答言語を設定する

組織の電話会議のダイヤルイン番号の言語を変更する方法については、「 [Microsoft Teams で電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)する」を参照してください。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>手順 8: (省略可能) 組織の電話会議ブリッジの設定を変更する

組織の電話会議ブリッジの設定を変更するには、「 [電話会議ブリッジの設定を変更](change-the-settings-for-an-audio-conferencing-bridge.md)する」を参照してください。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>手順 9: (省略可能) 組織内のユーザーの会議出席依頼に含まれる電話番号を設定する

ユーザーの会議出席依頼に含まれる電話番号のセットを変更するには、「 [Microsoft Teams の招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」を参照してください。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能

以下は、GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能です。

- 名前の記録を使用した入力通知と終了通知。 Direct Routing、entry、出口の通知を使った電話会議では、会議中にトーンが再生されます。

- 電話会議の発信通話制限ポリシー。 発信通話を制限するユーザーレベルのコントロールは、直接ルーティングによってルーティングされる会議のダイヤルアウト通話には適用されません。

- 会議固有の開催者の無料電話番号の使用を無効にします。 ユーザーレベルの制御。組織の会議に参加するための無料電話番号の使用を制限するには、直接ルーティングを使ってルーティングする必要はありません。

- ユーザー設定が変更された場合に通知メールをユーザーに送信する。 電話会議の通知メールは、GCC 高と DoD のダイレクトルーティングを使用した電話会議ではサポートされていません。
