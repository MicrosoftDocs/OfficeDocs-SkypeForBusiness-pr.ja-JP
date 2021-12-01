---
title: オペレーターと会議Connect構成する
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: オペレーター会議を構成する方法の詳細Connectします。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257524"
---
# <a name="configure-operator-connect-conferencing"></a>オペレーターと会議Connect構成する

この記事では、組織とユーザーのオペレーター Connect会議を構成する方法について説明します。

オペレーター Connect会議を構成する前に、特典と[](operator-connect-conferencing-plan.md)ライセンス要件の詳細については、「オペレーター Connect 会議の計画」を参照してください。

この記事で説明するトピックは次のとおりです。

- [演算子を設定する](#set-up-an-operator)
- [電話会議ブリッジの番号を取得する](#acquire-numbers-for-your-audio-conferencing-bridge)
- [ユーザーの会議出席招待に含まれる既定の電話番号を変更する](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [オペレーターを介して会議Microsoft Teams発信通話を送信する](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [オペレーターを管理する](#manage-your-operators)
- [電話会議ブリッジからのリリース番号](#release-numbers-from-your-audio-conferencing-bridge)
- [Microsoft 電話会議の管理に関する追加情報](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>演算子を設定する

管理センターでオペレーターを設定、編集、削除Teamsできます。 左側のナビゲーション ウィンドウで、[Voice > **演算子] に移動します**。

演算子を設定するには:

1. **演算子を選択します。**  [すべての演算子  **] タブで**、リージョンまたはサービス別に使用可能な演算子をフィルター処理して、音声ニーズに合った   適切な演算子を検索します。 次に、使用する演算子を選択します。 [オペレーター Connect会議] で、オペレーターが使用可能な製品として [会議] が表示されていないことを確認します。

2. **国を選択します。**  [ **演算子の設定]** で、選択した演算子で有効にする国を選択します。

3. **連絡先情報を入力する**  氏名やメール アドレスなどの連絡先情報は、オペレーターと共有されます。 この情報は後で変更できます。 さらに、電話番号を指定するオプションを指定して、会社の規模を指定する必要があります。 オペレーターは、この情報を使用して、オペレーターと会議の詳細についてConnectします。

4. データ転送に関する通知に同意します。

5. **演算子を追加します。**  [Add  **as my operator]を選択して**   保存します。

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>電話会議ブリッジの番号を取得する

組織の電話会議ブリッジには、組織内のすべてのユーザーが PSTN 電話番号を使用して会議に参加できるMicrosoft Teams電話番号が含まれています。 組織の電話会議ブリッジに関連付けられている電話番号は、Teams 管理センターの [会議ブリッジ] の下>**確認できます**。

電話会議ブリッジの電話番号を取得するには、次の手順に従います。

1. **電話会議 Standard サブスクリプションまたはオペレーター Connectライセンス。** 開催する会議に参加するためにオペレーター Connect 会議番号が必要なユーザーには、電話会議 Standard サブスクリプション ライセンスまたはオペレーター Connect 会議ライセンスが割り当てられている必要があります。 詳細については、「オペレーター会議の[計画」をConnectしてください](operator-connect-conferencing-plan.md)。

2. **数値を取得します。**  オペレーターの Web サイトに移動して、電話番号を注文して取得します。 オペレーターの Web サイトの一覧については、オペレーターのMicrosoft 365 [ディレクトリConnectしてください](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 テナント ID を指定する必要があります。 テナント ID が分からない場合は、「テナント ID を検索[する」Microsoft 365参照してください](/onedrive/find-your-office-365-tenant-id)。 オペレーターが注文を完了すると、テナントに番号がアップロードされます。 [音声と番号] に移動すると、Teams管理センターで **番号とプロバイダー> 電話できます**。

3. **電話会議ブリッジに番号を割り当てる。** 電話会議ブリッジに番号を割り当てるには、Teams 管理センターの [会議> 会議ブリッジ] >**追加します**。 詳細については、「電話会議ブリッジ [で電話番号を変更する」を参照してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

>[!NOTE]
>ブリッジの既定の番号としてConnect電話会議番号を割り当てできません。 電話番号が電話会議ブリッジに割り当てられると、電話会議ライセンスまたはオペレーター Connect 会議ライセンスを持つ組織内のユーザーの会議出席招待に含まれる [ローカル番号の検索] ページに番号が一覧表示されます。
>
>オペレーターを介して発信通話をルーティングするには、この[](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)記事の「オペレーターを介した Teams 会議からの発信通話の送信」セクションを参照してください。

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>ユーザーの会議出席招待に含まれる既定の電話番号を変更する

 この手順は省略可能です。

ユーザーの既定の電話番号は、会議のスケジュールを設定するときに会議の招待に含まれる電話番号です。 Teams 管理センターの [ユーザーの管理] で、ユーザーの会議出席>**を更新できます**。 ユーザーの会議出席招待に含まれる電話番号を更新するには、ユーザーを選択し、[電話会議] セクションで [編集 **] を選択** します。

変更が適用されると、開催者の新しい会議出席招待に新しい既定の電話番号が含まれます。 ただし、変更前にスケジュールされた既存の会議出席招待では、元の既定の番号が保持されます。

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>オペレーターを介して会議Microsoft Teams発信通話を送信する

Microsoft 電話会議 Standard サブスクリプションまたはオペレーター Connect 会議ライセンスをお持ちである場合は、電話会議ルーティング ポリシーを設定して、オペレーターを介して Teams 会議からの発信通話のすべてまたはセットをルーティングする電話会議サービスを構成できます。

>[!NOTE]
>電話会議ライセンスConnect、発信通話はオペレーター経由でのみ行います。 Operator Connect 会議ライセンスをお持ちである場合は、以下の説明に従ってサービスを構成して、Teamsから電話番号への発信通話を有効にする必要があります。

電話会議ルーティング ポリシーはユーザー レベルで適用できます。つまり、オペレーターは、関連付けられたポリシーを持つユーザーによって開催された Teams 会議からの発信通話のみをルーティングします。 グローバル レベルでこれらのポリシーを適用することもできます。つまり、オペレーターは組織内のすべてのユーザーが開催する Teams 会議からの発信通話をルーティングします。

PowerShell を使用して、組織の新しい電話会議ルーティング ポリシーを作成します。 Teams 会議からの発信通話のプライマリ ルートとしてオペレーターを指定するには、次に示す PowerShell コマンドを使用して手順に従います。

1. [手順 1: オンライン PSTN 使用法ポリシーに新しい文字列を追加する](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [手順 2: 新しいオンライン音声ルート ポリシーを作成する](#step-2-create-a-new-online-voice-route-policy)
3. [手順 3: 新しいオンライン電話会議ルーティング ポリシーを作成する](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [手順 4: 新しいポリシーをユーザーに割り当てる](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>手順 1: オンライン PSTN 使用法ポリシーに新しい文字列を追加する

この [コマンドレットの使用の詳細については、「Set-CsOnlinePstnUsage」](/powershell/module/skype/set-csonlinepstnusage) を参照してください。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>手順 2: 新しいオンライン音声ルート ポリシーを作成する

この [コマンドレットの使用の詳細については、「Set-CsOnlineVoiceRoute」](/powershell/module/skype/set-csonlinevoiceroute) を参照してください。

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>手順 3: 新しいオンライン電話会議ルーティング ポリシーを作成する

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>手順 4: 新しいポリシーをユーザーに割り当てる

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>電話会議ルーティング ポリシーをグローバルとして設定し、組織内のすべてのユーザーに適用するには、 パラメーターの代わりに パラメーター ``-Global`` を使用 ``-Identity`` します。 たとえば、 ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` です。

電話会議ルーティング ポリシーを作成してユーザーに適用すると、パラメーターで指定された電話番号を提供するオペレーターは、PSTN 電話番号への発信Teamsをルーティングします ``BridgeSourcePhoneNumber`` 。 さらに、 パラメーターは、PSTN 電話番号への発信通話の発信回線識別電話番号として使用する ``BridgeSourcePhoneNumber`` 電話番号を指定します。

で指定されたパターンは正規表現形式であり、演算子を介してルーティングする呼び出 ``NumberPattern`` しを指定します。 上記 ``"\d+"`` の例のパターンは、すべての発信通話と一致し、Teamsします。 NumberPattern パラメーターを として設定することもできます。このパラメーターは  ``“^\+1(425|206)(\d{7})$”`` 、+1 425 XXX XX XX または +1 206 XXX XX XX の形式でダイヤルされた番号と一致します。これは、+1 ``“^\+1(\d{10})$”`` 425 XXX XX XX という形式のダイヤルされた番号に一致します。

電話会議ルーティング ポリシーをユーザーに割り当てると、会議から電話会議ルーティング ポリシーで指定されている正規表現に一致する電話番号へのすべての呼び出しは、オペレーターを介してルーティングされます。また、[他のユーザーを招待またはダイヤルする] オプションを使用して開始された通話や通話を含む。

## <a name="manage-your-operators"></a>オペレーターを管理する

[演算子 **] タブ** から、演算子とその状態を表示し、選択内容に次の   変更を加えます。

- 国別にオペレーター サービスを管理する
- 演算子を中断する
- 演算子を削除する

>[!NOTE]
>組織または国からオペレーターを削除する前に、ユーザーと電話会議ブリッジに割り当てられているすべての電話番号を削除してから、オペレーターに連絡して番号を解放する必要があります。

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>電話会議ブリッジからのリリース番号

Teams 管理センターから電話会議ブリッジから電話番号を解放するには、「電話会議ブリッジの電話番号を変更する」の「会議ブリッジのサービス電話番号を割り当て解除する手順」を[参照](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)してください。

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Microsoft 電話会議の管理に関する追加情報

組織の Microsoft 電話会議を管理する方法の詳細については、次の記事を参照してください。

- 組織の Microsoft 電話会議サービス設定の管理[Microsoft Teams:](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)組織の電話会議設定を管理する

- 組織内のユーザーの Microsoft 電話会議サービス設定の管理: 組織内のユーザーの電話会議設定[を管理Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 電話会議の電話番号の自動応答言語を変更[する:](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)電話会議の自動応答言語を設定Microsoft Teams
