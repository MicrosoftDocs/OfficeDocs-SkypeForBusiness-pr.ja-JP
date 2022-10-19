---
title: オペレーター接続会議を構成する
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
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: オペレーター接続会議を構成する方法の詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b31c66e2621051ed96c13d6f414eec9dadb02495
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585073"
---
# <a name="configure-operator-connect-conferencing"></a>オペレーター接続会議を構成する

この記事では、組織とユーザーのオペレーター接続会議を構成する方法について詳しく説明します。

オペレーター接続会議を構成する前に、特典とライセンス要件の詳細については、「[オペレーター接続会議の計画](operator-connect-conferencing-plan.md)」を参照してください。

この記事で取り上げるトピックは次のとおりです。

- [演算子を設定する](#set-up-an-operator)
- [電話会議ブリッジの番号を取得する](#acquire-numbers-for-your-audio-conferencing-bridge)
- [ユーザーの会議出席依頼に含まれる既定の電話番号を変更する](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [オペレーターを介して Microsoft Teams 会議から発信通話を送信する](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [オペレーターを管理する](#manage-your-operators)
- [電話会議ブリッジから番号をリリースする](#release-numbers-from-your-audio-conferencing-bridge)
- [Microsoft 電話会議の管理に関する追加情報](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>演算子を設定する

Teams 管理センターでオペレーターを設定、編集、削除できます。 左側のナビゲーション ウィンドウで、[ **音声>演算子**] に移動します。

演算子を設定するには:

1. **演算子を選択します。** [ **すべての演算子** ] タブで、使用可能な演算子をリージョンまたはサービス別にフィルター処理して、音声ニーズに適した演算子を見つけます。 次に、使用する演算子を選択します。 オペレーター接続会議については、オペレーターが使用可能な製品として **会議が** 一覧表示されていることを確認します。

2. **国を選択します。** [ **オペレーターの設定**] で、選択した演算子で有効にする国を選択します。

3. **連絡先情報を入力する** 完全な名前と電子メール アドレスを含む連絡先情報は、オペレーターと共有されます。 この情報は後で変更できます。 さらに、電話番号を指定するオプションを使用して、会社の規模を指定する必要があります。 オペレーターはこの情報を使用して、オペレーター接続会議に関する詳細を連絡します。

4. データ転送に関する通知を受け入れます。

5. **演算子を追加します。** 保存 **する演算子として追加** を選択します。

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>電話会議ブリッジの番号を取得する

組織の電話会議ブリッジには、組織内のすべてのユーザーが PSTN 電話番号を使用して Microsoft Teams 会議に参加できる電話番号が含まれています。 Teams 管理 センターの会議>会議ブリッジで、組織の電話会議ブリッジに関連付けられている電話番号 **を** 確認できます。

電話会議ブリッジの電話番号を取得するには、次の手順に従います。

1. **電話会議 Standard サブスクリプションまたはオペレーター接続会議 ライセンス。** 組織する会議に参加するためにオペレーター接続会議番号が必要なユーザーは、電話会議標準サブスクリプション ライセンスまたはオペレーター接続会議 ライセンスが割り当てられている必要があります。 詳細については、「[オペレーター接続会議の計画」を](operator-connect-conferencing-plan.md)参照してください。

2. **数値を取得します。** オペレーターの Web サイトに移動して、電話番号を注文して取得します。 オペレーター Web サイトの一覧については、 [Microsoft 365 Operator Connect ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照してください。 テナント ID を指定する必要があります。 テナント ID がわからない場合は、「 [Microsoft 365 テナント ID を検索する](/onedrive/find-your-office-365-tenant-id)」を参照してください。 オペレーターが注文を完了すると、番号がテナントにアップロードされます。 **Voice >の電話番号** に移動すると、Teams 管理センターで番号とプロバイダーを表示できます。

3. **電話会議ブリッジに番号を割り当てます。** 電話会議ブリッジに番号を割り当てるには、[ **会議] > [会議ブリッジ] > [追加]** の [Teams 管理センター] から行います。 詳細については、「 [電話会議ブリッジの電話番号を変更する」を参照してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

>[!NOTE]
>ブリッジの既定の番号としてオペレーター接続会議番号を割り当てることはできません。 電話会議ブリッジに電話番号が割り当てられると、[電話会議ライセンスまたはオペレーター接続会議 ライセンスを持つ組織内のユーザーの会議への招待に含まれる **ローカル番号の検索] ページ** に番号が一覧表示されます。
>
>オペレーターを介して発信通話をルーティングするには、この記事の「オペレーター [**を介して Teams 会議から発信通話を送信する**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) 」セクションを参照してください。

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>ユーザーの会議出席依頼に含まれる既定の電話番号を変更する

 この手順は省略可能です。

ユーザーの既定の電話番号は、会議をスケジュールするときに会議の招待に含まれる電話番号です。 Teams 管理 センターの [ユーザー>**ユーザーの管理**] で、ユーザーの会議出席依頼に含まれる電話番号を更新できます。 ユーザーの会議出席依頼に含まれる電話番号を更新するには、ユーザーを選択し、[**電話会議**] セクションで **[編集]** を選択します。

変更が適用されると、開催者の新しい会議出席依頼に新しい既定の電話番号が含まれます。 ただし、変更前にスケジュールされた既存の会議出席依頼は、元の既定の番号を保持します。

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>オペレーターを介して Microsoft Teams 会議から発信通話を送信する

Microsoft 電話会議 Standard サブスクリプションまたはオペレーター接続会議 ライセンスをお持ちの場合は、電話会議ルーティング ポリシーを設定することで、オペレーターを介して Teams 会議からの発信通話のすべてまたはセットをルーティングするように電話会議サービスを構成できます。

>[!NOTE]
>オペレーター接続会議 ライセンスを使用すると、発信呼び出しはオペレーターのみを経由できます。 オペレーター接続会議 ライセンスがある場合は、Teams 会議から電話番号への発信通話を有効にするには、以下で説明するようにサービスを構成する必要があります。

ユーザー レベルで電話会議ルーティング ポリシーを適用できます。つまり、オペレーターは、関連付けられたポリシーを持つユーザーが編成した Teams 会議からの発信通話のみをルーティングします。 また、これらのポリシーをグローバル レベルで適用することもできます。つまり、オペレーターは組織内のすべてのユーザーが組織する Teams 会議からの発信通話をルーティングします。

PowerShell を使用して、組織の新しい電話会議ルーティング ポリシーを作成します。 Teams 会議からの発信通話の主なルートとしてオペレーターを指定するには、次に示す PowerShell コマンドを使用して次の手順に従います。

1. [手順 1: オンライン PSTN 使用法ポリシーに新しい文字列を追加する](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [手順 2: 新しいオンライン 音声ルート ポリシーを作成する](#step-2-create-a-new-online-voice-route-policy)
3. [手順 3: 新しいオンライン電話会議ルーティング ポリシーを作成する](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [手順 4: 新しいポリシーをユーザーに割り当てる](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>手順 1: オンライン PSTN 使用法ポリシーに新しい文字列を追加する

このコマンドレットの使用の詳細については、 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) を参照してください。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>手順 2: 新しいオンライン 音声ルート ポリシーを作成する

このコマンドレットの使用の詳細については、 [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) を参照してください。

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>手順 3: 新しいオンライン電話会議ルーティング ポリシーを作成する

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>手順 4: 新しいポリシーをユーザーに割り当てる

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>電話会議ルーティング ポリシーをグローバルに設定し、組織内のすべてのユーザーに適用するには、パラメーターの代わりにパラメーターを``-Identity``使用``-Global``できます。 たとえば、 ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``.

電話会議ルーティング ポリシーを作成してユーザーに適用すると、パラメーターで ``BridgeSourcePhoneNumber`` 指定された電話番号を提供するオペレーターは、Teams の発信通話を PSTN 電話番号にルーティングします。 さらに、このパラメーターは ``BridgeSourcePhoneNumber`` 、PSTN 電話番号への発信通話の発信回線識別電話番号として使用する電話番号を指定します。

正規表現形式で ``NumberPattern`` 指定されるパターンは、演算子を介してルーティングする呼び出しを指定します。 上の例のパターンは ``"\d+"`` 、Teams 会議からのすべての送信呼び出しと一致します。 NumberPattern パラメーター  ``"^\+1(425|206)(\d{7})$"``は、ダイヤルされた番号と次の形式で一致するように設定することもできます。+1 425 XXX XX XX または +1 206 XXX XX XX、または ``"^\+1(\d{10})$"``ダイヤルされた番号と次の形式で一致します: +1 425 XXX XX XX。

ユーザーに電話会議ルーティング ポリシーを割り当てると、電話会議ルーティング ポリシーで指定された正規表現に一致する電話番号に会議からのすべての通話が、オペレーターを経由してルーティングされます(通話 **時の通話** や、 **他のユーザーの招待または番号** 会議オプションを使用して開始された通話を含む)。

## <a name="manage-your-operators"></a>オペレーターを管理する

[ **個人用演算子** ] タブから、演算子とその状態を表示し、選択内容に次の変更を加えることができます。

- 国別にオペレーター サービスを管理する
- 演算子を中断する
- 演算子を削除する

>[!NOTE]
>組織または国からオペレーターを削除する前に、ユーザーと電話会議ブリッジに割り当てられているすべての電話番号を削除してから、オペレーターに連絡して番号を解放する必要があります。

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>電話会議ブリッジから番号をリリースする

Teams 管理センターから電話会議ブリッジから電話番号を解放するには、「電話会議ブリッジの電話番号を変更する」の **「会議ブリッジのサービス電話番号の割り当てを解除する場合の手順** 」を参照 [してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)。

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Microsoft 電話会議の管理に関する追加情報

組織の Microsoft 電話会議を管理する方法の詳細については、次の記事を参照してください。

- 組織の Microsoft 電話会議サービス設定の[管理: Microsoft Teams で組織の電話会議設定を管理](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)する

- 組織内のユーザーの Microsoft 電話会議サービス設定の[管理: Microsoft Teams のユーザーの電話会議設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する

- 電話会議の電話番号の自動応答言語を変更する: [Microsoft Teams で電話会議の自動応答言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
