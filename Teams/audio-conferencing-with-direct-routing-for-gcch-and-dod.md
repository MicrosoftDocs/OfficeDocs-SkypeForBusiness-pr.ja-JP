---
title: GCCH と DoD のダイレクトルーティングを使用した電話会議
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
localization_priority: Normal
description: GCCH および DoD 環境で直接ルーティングを使用して電話会議を使用する方法について説明します。
ms.openlocfilehash: 67c8a8b3ec16f36a93eb4561473facacdbd85464
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516736"
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

  ```
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

次に例を示します。
  ```
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>サービスの電話番号を組織の電話会議ブリッジに割り当てる

Set-csonlinedialinconferencingservicenumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービスの電話番号を割り当てることができます。

  ```
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Get-csonlinedialinconferencingbridge を使用して、電話会議ブリッジの ID を確認できます。 次に例を示します。

  ```
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>手順 4: ユーザーに GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議を割り当てる

スマートなスマート電話会議をユーザーに対して、GCC 高または DoD ライセンスのダイレクトルーティングで割り当てるには、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)」を参照してください。

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>手順 5: (オプション) Teams で電話会議番号のリストを表示する

組織の電話会議番号の一覧を表示するには、 [「Microsoft Teams で電話会議番号のリストを表示する」](see-a-list-of-audio-conferencing-numbers-in-teams.md)を参照してください。

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>手順 6: (省略可能) 組織の電話会議のダイヤルイン番号用に自動応答言語を設定する

組織の電話会議のダイヤルイン番号の言語を変更する方法については、「 [Microsoft Teams で電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)する」を参照してください。

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>手順 7: (省略可能) 組織の電話会議ブリッジの設定を変更する

組織の電話会議ブリッジの設定を変更するには、「[電話会議ブリッジの設定を変更](change-the-settings-for-an-audio-conferencing-bridge.md)する」を参照してください。

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>手順 8: (省略可能) 組織内のユーザーの会議出席依頼に含まれる電話番号を設定する

ユーザーの会議出席依頼に含まれる電話番号のセットを変更するには、「 [Microsoft Teams の招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」を参照してください。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能

以下は、GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能です。

- 名前の記録を使用した入力通知と終了通知。 Direct Routing、entry、出口の通知を使った電話会議では、会議中にトーンが再生されます。

- 電話会議の発信通話制限ポリシー。 発信通話を制限するユーザーレベルのコントロールは、直接ルーティングによってルーティングされる会議のダイヤルアウト通話には適用されません。

- 会議固有の開催者の無料電話番号の使用を無効にします。 ユーザーレベルの制御。組織の会議に参加するための無料電話番号の使用を制限するには、直接ルーティングを使ってルーティングする必要はありません。

- ユーザー設定が変更された場合に通知メールをユーザーに送信する。 電話会議の通知メールは、GCC 高と DoD のダイレクトルーティングを使用した電話会議ではサポートされていません。
