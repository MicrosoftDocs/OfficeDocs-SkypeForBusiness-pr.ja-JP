---
title: 会議ポリシーを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Teams で会議ポリシーの設定を管理する方法について説明します。また、会議ポリシーの設定を使用して、ユーザーがスケジュールした会議の参加者に対して利用できる機能を制御します。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598761"
---
# <a name="manage-meeting-policies-in-teams"></a>Teams での会議ポリシーを管理する

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。 自動的に作成されるグローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成して割り当てることもできます。 会議ポリシーは、Microsoft Teams 管理センターで管理するか、[PowerShell](teams-powershell-overview.md) を使用して管理します。

> [!NOTE]
> ロールを使用して、会議の発表者や出席者の権限を管理する方法の詳細については、「[Teams会議の役割](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」を参照してください。

次の方法でポリシーを実装できます。これらの方法は、会議の開始前、会議中、または会議後のユーザーの会議エクスペリエンスに影響します。

|実装の種類  |説明  |
|---------|---------|
|開催者単位    |開催者単位のポリシーを実装すると、すべての参加者は開催者のポリシーを継承します。 たとえば、[**ユーザーの参加を自動的に許可する**] は、開催者単位のポリシーであり、ユーザーが会議に直接参加するか、ポリシーが割り当てられたユーザーがスケジュールした会議をロビーで待機するかを制御します。          |
|ユーザーごと    |ユーザーごとのポリシーを実装すると、ユーザーごとのポリシーのみが適用され、開催者や会議参加者に対する特定の機能が制限されます。 たとえば、[**チャネルで "今すぐ会議" を許可する**] は、ユーザー単位のポリシーです。     |
|開催者単位およびユーザーごと     |開催者単位とユーザー単位のポリシーを組み合わせて実装すると、会議の参加者はユーザーのポリシーと開催者のポリシーに基づいて特定の機能が制限されます。 たとえば、[**クラウド記録を許可する**] は、開催者単位およびユーザーごとのポリシーです。 この設定をオンにすると、会議の開催者と参加者は記録の開始と停止が可能になります。

グローバル ポリシーの設定を編集したり、1 つまたは複数のカスタム ポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てていない場合、ユーザーにはグローバル ポリシーが適用されます。

> [!NOTE]
> [会議の詳細] ボタンは、ユーザーがオーディオ会議ライセンスを有効にしているか、ユーザーがオーディオ会議に許可されている場合に使用できます。それ以外の場合、会議の詳細は利用できません。

## <a name="create-a-custom-meeting-policy"></a>カスタムのチーム ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。 名前に特殊文字を含めたり、64 文字より長くすることはできません。
4. 希望する設定を選びます。
5. **[保存]** をクリックします。

たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。 「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。

[**オーディオとビデオ**] で、

- [クラウド記録を許可する] を無効にします。
- [IP のビデオを許可する] を無効にします。

[**コンテンツの共有**] で、

- 画面共有モードを無効にします。
- [ホワイトボードを許可] を無効にします。
- [メモの共有を許可する] を無効にします。

その後、ポリシーをユーザーに割り当てます。

## <a name="edit-a-meeting-policy"></a>会議 ポリシーの編集

グローバル ポリシーおよび作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. ここで、希望する変更を行います。
4. **[保存]** をクリックします。

> [!NOTE]
> ユーザーに割り当てることができる会議ポリシーは一度に 1 つのみです。

## <a name="assign-a-meeting-policy-to-users"></a>ユーザーに会議ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> ユーザーが割り当てられているポリシーは削除できません。 影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。

## <a name="meeting-policy-settings"></a>会議ポリシーの設定

[**会議ポリシー**] ページで既存のポリシーを選択するか、新しいポリシーを追加するための [**追加**] を選択すると、次の設定内容を構成できます。

- [全般](meeting-policies-in-teams-general.md)
- [オーディオとビデオ](meeting-policies-audio-and-video.md)
- [コンテンツの共有](meeting-policies-content-sharing.md)
- [参加者とゲスト](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
- [ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する](meeting-policies-restricted-anonymous-access.md)