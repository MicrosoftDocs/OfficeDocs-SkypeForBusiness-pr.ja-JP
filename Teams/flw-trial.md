---
title: Teamsでフロントライン試用版を管理する
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織のフロントライン ワーカー試用版に 90 日間のTeamsを設定する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758298"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Teamsでフロントライン試用版を管理する

> [!NOTE]
> この試用版のエクスペリエンスは近日公開予定です。 組織で利用可能な場合は、Microsoft 365 管理 [センターのメッセージ センターでメッセージ](https://go.microsoft.com/fwlink/p/?linkid=2070717)を探して確認できます。

Microsoft Teamsフロントライン 試用版エクスペリエンスを使用すると、組織内のユーザーがTeams、他のメンバーがAzure Active Directory (Azure AD) にいる限り、フロントライン チーム全体のTeams エクスペリエンスを開始できます。 [AllowSelfServicePurchase PowerShell モジュール](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)を使用して、組織内のユーザーに対してこの機能を無効にすることができます。

## <a name="what-services-are-included"></a>どのようなサービスが含まれているか

試用版には、次の例外を除き[、Microsoft 365 F3 ライセンス](https://www.microsoft.com/microsoft-365/enterprise/f3)に含まれるものがすべて含まれています。

- フロントライン試用版には、キオスクではなくExchange Foundation Exchange含まれています。 この変更により、ユーザーが他のTeams機能を失う可能性があります。

## <a name="eligibility"></a>資格

> [!NOTE]
> 組織が試用版パイロットの一部であるかどうかを確認するには、Microsoft 365 管理 [センターのメッセージ センター](https://go.microsoft.com/fwlink/p/?linkid=2070717)でお知らせを探します。 ユーザーが試用版を開始または参加するには、組織が試用版パイロットの一部である必要があります。 このプランは、GCC、GCC High、DoD、EDU のお客様はご利用いただけません。

フロントライン 試用版は、試用版あたり最大 300 人のユーザーに対応できます。

ユーザーは、次の場合にチームのフロントライン 試用版を開始できます。

- Teamsへのアクセス権を付与するアクティブなライセンスを持っている。
- 現場のワーカー試用版をまだ開始していません。

> [!IMPORTANT]
> 試用版が終了する前に試用版を開始したユーザーが組織を離れた場合、管理者は試用版を監視し、チームにチェックインして、これらの機能の恩恵を受けているユーザーを確認し、有料ライセンスにアップグレードする必要があるユーザーを決定する必要があります。

ユーザーは、マネージド Azure Active Directory ドメインの電子メール アドレスを持っている場合、フロントライン ワーカー試用版に参加できます。

ユーザーは、以前に試用版を開始したが、別の試用版を開始できない場合は参加できます。

> [!NOTE]
> Teamsに既存のアクセス権を持たないユーザーは、チームの作成時にのみ試用版チームに追加できます。 既存のTeams ユーザーは、チームの作成後も試用版に追加できます。

## <a name="set-up-the-trial"></a>試用版を設定する

対象ユーザーは、デスクトップアプリまたは [Web](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks) アプリからTeamsでタスク アプリにサインインすることで、フロントライン試用版を開始できます。 現時点では、モバイルによるフロントライン 試用版の開始はサポートされていません。 試用版が開始されると、チーム全体にフロントライン 試用版ライセンスが自動的に割り当てられます。 Teamsにアクセスできる既存の有料ライセンスを持つユーザーには、試用版ライセンスも割り当てられますが、試用版全体を通じて既存のライセンスの機能を維持し、試用版終了後も既存の有料ライセンスを保持します。 試用版を開始したユーザーは、試用版の過程を通じて電子メール通知を受け取ります。

## <a name="manage-the-frontline-trials-experience"></a>最前線の試用版エクスペリエンスを管理する

管理者は、 **AllowSelfServicePurchase** PowerShell モジュールを使用して、エンド ユーザーが組織内でフロントライン 試用版を開始できないようにすることができます。 これは試用版ライセンスの場合のみです。 [AllowSelfServicePurchase PowerShell モジュールを使用する方法について説明](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)します。

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Frontline 試用版ライセンスを持つユーザーのTeamsを管理する

通常の有料ライセンスを持つユーザーを管理する場合と同様に、フロントライン 試用版ライセンスを持つユーザーを管理できます。 詳細については、「[組織の Teams 設定を管理する](/microsoftteams/manage-teams-overview)」を参照してください。

### <a name="remove-a-trial-license"></a>試用版ライセンスを削除する

PowerShell またはMicrosoft 365 管理センターを使用して、フロントライン 試用版ライセンスを削除できます。

[PowerShell を使用して削除する方法について説明します](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)。

[管理センターで削除する方法について説明します](/microsoft-365/admin/add-users/delete-a-user)。

## <a name="upgrade-users-from-frontline-trial"></a>フロントライン 試用版からユーザーをアップグレードする

ユーザーは、試用版の終了時にライセンスの要求を求める連絡を受ける場合があります。 ユーザーをアップグレードするには、管理者特権が必要です。

### <a name="when-to-upgrade"></a>アップグレードするタイミング

90 日間の試用版の終了間近で、有料ライセンスを継続する必要があるユーザーをユーザーに確認する必要があります。 フロントライン 試用版サブスクリプションの有効期限が切れる前に、ユーザーのエクスペリエンスが中断されないようにしてください。

> [!IMPORTANT]
> フロントライン 試用版ライセンスが終了し、ユーザーにTeamsを含むライセンスがすぐに割り当てられていない場合、ユーザーはTeamsにアクセスできなくなります。 30 日後、データ (ファイル、メッセージなど) が削除されます。 ユーザーは引き続き Azure Active Directory に残ります。 30 日以内にTeams機能を有効にするために新しいライセンスがユーザーに割り当てられている場合、Teams内のすべてのコンテンツは引き続き存在します。

### <a name="choose-an-upgrade-path"></a>アップグレード パスを選択する

> [!TIP]
> フロントライン 試用版は、[Microsoft 365 F3 ライセンス](https://www.microsoft.com/microsoft-365/enterprise/f3)に基づいています。

組織が現在持っているサブスクリプションに応じて、フロントライン 試用版から有料ライセンスにアップグレードするには、次の 3 つの方法があります。

- **既存の Microsoft 365 サブスクリプションをアップグレードします。** 組織に Teams を含まない他の Office 製品のサブスクリプションがある場合は、このオプションを使用します。 詳細については、「 [別のプランへのアップグレード」を](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan)参照してください。 既存のサブスクリプションのアクティブなユーザーを表示するには、Microsoft 365 管理センターの **[ユーザー] >** [[アクティブなユーザー]](https://go.microsoft.com/fwlink/p/?linkid=834822) に移動します。

- **既存の Microsoft 365 サブスクリプションを追加します。** 組織に、フロントライン チームをカバーするのに十分な有料Teamsライセンスがない場合は、このオプションを使用します。 詳細については、「[ライセンスの購入/削除](/microsoft-365/commerce/licenses/buy-licenses)」をご覧ください。 すでに十分な使用可能なライセンスがある既存のサブスクリプションにユーザーを追加するには、「[ユーザーを別のサブスクリプションに移動する](/microsoft-365/commerce/subscriptions/move-users-different-subscription)」を参照してください。 既存のサブスクリプションのアクティブなユーザーを表示するには、Microsoft 365 管理センターの **[ユーザー] >** [[アクティブなユーザー]](https://go.microsoft.com/fwlink/p/?linkid=834822) に移動します。

- **新しい Microsoft 365 サブスクリプションを購入する** 組織に製品をOfficeする既存のサブスクリプションがない場合、または組織が既存のサブスクリプションと異なるサブスクリプションを購入してフロントライン ユーザーをカバーする場合は、このオプションを使用します。 詳細については、「[Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline)」を参照してください。

アップグレードするサブスクリプションMicrosoft 365不明な場合は、[Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline)を参照してください。 サブスクリプションの選択についてさらにサポートが必要な場合、または組織で 300 を超えるライセンスが必要な場合は、[Microsoft パートナー](https://www.microsoft.com/solution-providers/home)または Microsoft アカウント担当者にお問い合わせください。

### <a name="assign-paid-licenses"></a>有料ライセンスを割り当てる

新しく取得したライセンスを割り当てるには、「[ユーザーにライセンスを割り当てる](/microsoft-365/admin/manage/assign-licenses-to-users)」をご覧ください。  

新しいライセンスを割り当てたら、Teams Exploratory ライセンスの割り当てを解除します。 詳細については、「[ユーザーからライセンスの割り当てを解除する](/microsoft-365/admin/manage/remove-licenses-from-users)」を参照してください。

## <a name="faq"></a>よくあるご質問 (FAQ)

**試用版の有効期間** <br>
フロントライン 試用版は 90 日間続きます。

**90 日間のフロントライン 試用版エクスペリエンスの終了時に管理者は何を行う必要がありますか?** <br>
90 日間の試用版の終了時に、有料ライセンスを継続する必要があるユーザーをユーザーに確認する必要があります。 その後、 [ユーザーをアップグレード](#upgrade-users-from-frontline-trial)する必要があります。

**試用版を開始したユーザーが組織を離れた場合はどうなりますか?** <br>
管理者は、残りの 90 日間試用版を監視し、試用版の終了時に必要なユーザーの有料ライセンスにアップグレードする必要があります。

**データ保持ポリシーとは何ですか?** <br>
データリテンション期間については、[Microsoft 365サブスクリプション情報](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?)から確認できます。

**フロントライン 試用版の開始時にユーザーにエラーが発生した場合はどうなりますか?** <br>
組織、試用版を開始するユーザー、試用版に追加されるユーザーが [適格性の条件](#eligibility)を満たしていることを確認します。