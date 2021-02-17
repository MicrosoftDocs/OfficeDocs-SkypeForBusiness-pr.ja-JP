---
title: Microsoft Teams でのコール パークおよび保留解除
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Microsoft Teams でコール パークを使用して通話を保留する方法について説明します。
ms.openlocfilehash: 7474b80975c5fc78285a8bba5a90de782f24ba5b
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260329"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams でのコール パークおよび保留解除

コール パークと取得は、ユーザーが通話を保留にできる機能です。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話をパークしたユーザーまたは他のユーザーは、サポートされているアプリまたはデバイスでそのコードを使用して通話を取得できます。 (詳細については [、「Teams で通話をパークする」](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) を参照してください)。

コール パークを使用する一般的なシナリオには、次のようなものがあります。

- 受付が、工場で働く人宛にかかってきた通話を保留にします。 次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。 通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。
- バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。 その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。
- サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。 エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。

通話をパークして取得するには、ユーザーがユーザーのエンタープライズ VoIPであり、コール パーク ポリシーに含める必要があります。

> [!NOTE]
> コール パークと取得は [、Teams 展開](teams-and-skypeforbusiness-coexistence-and-interoperability.md) モードでのみ使用できます。Skype for Business IP 電話機ではサポートされていません。

## <a name="configure-call-park-and-retrieve"></a>コール パークを構成して取得する

通話パークを構成して取得するには、Teams 管理者である必要があります。 既定では無効になっています。 コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。 一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。

コール パーク ポリシーを有効にするには

1. Microsoft Teams 管理センターの左側のナビゲーションで、**音声** 通話パークのポリシー  >  **に移動します**。
2. [ポリシーの **管理] タブの [** 追加] を **クリックします**。
3. ポリシーに名前を付け、[通話パークの許可] を [オン] **に** 切り **替えます**。

    ![コール パーク ポリシー設定のスクリーンショット](media/call-park-add-policy.png)

4. **[保存]** を選択します。

ポリシーを編集するには、一覧でポリシーを選び、[編集] をクリック **します**。

ポリシーを機能するには、ポリシーをユーザーに割り当てる必要があります。 ポリシーを [ユーザーに個別に割り当てるか](assign-policies.md) 、グループに割り当てできます。

グループに通話パーツ ポリシーを割り当てるには

1. [コール **パーク ポリシー] ページの [** グループ ポリシーの割り当 **て** ] タブで、[グループの **追加] をクリックします**。
2. 使用するグループを検索し、[追加] をクリック **します**。
3. 他のグループ割り当てと比較してランクを選択します。
4. [ **ポリシーの選択]** で、このグループを割り当てるポリシーを選択します。

    ![](media/call-park-assign-policy-to-group.png)

5. [**適用**] をクリックします。

## <a name="related-topics"></a>関連項目

[Teams で通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
