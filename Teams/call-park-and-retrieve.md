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
description: Microsoft Teams で通話パークを使用して通話を保留にする方法について説明します。
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424595"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams でのコール パークおよび保留解除

コールパークと取得は、ユーザーが通話を保留にできる機能です。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留にしたユーザーは、サポートされているアプリまたはデバイスでそのコードを使って通話を取得できます。 (詳細について [は、「Teams で通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 」を参照してください)。

コール パークを使用する一般的なシナリオには、次のようなものがあります。

- 受付が、工場で働く人宛にかかってきた通話を保留にします。 次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。 通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。
- バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。 その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。
- サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。 エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。

通話をパークして取得するには、ユーザーがエンタープライズボイスユーザーであり、コールパークポリシーに含まれている必要があります。

> [!NOTE]
> コールパークと取得は [Teams のみの展開モード](teams-and-skypeforbusiness-coexistence-and-interoperability.md) でのみ使用でき、Skype for BUSINESS の IP 電話ではサポートされません。

## <a name="configure-call-park-and-retrieve"></a>コールパークの構成と取得

コールパークを構成して取得するには、Teams の管理者である必要があります。 既定では無効になっています。 コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。 一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。

コールパークポリシーを有効にするには

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **通話パークポリシー**] に移動します。
2. [ **ポリシーの管理** ] タブの [ **追加**] をクリックします。
3. ポリシーに名前を付け、[ **call パークを有効**にする] に切り替え**ます。**

    ![コールパークポリシー設定のスクリーンショット](media/call-park-add-policy.png)

4. **[保存]** を選択します。

リストでポリシーを選択して [ **編集**] をクリックすると、ポリシーを編集できます。

ポリシーが機能するためには、そのポリシーがユーザーに割り当てられている必要があります。 [ポリシーは、ユーザーに個別に割り当てる](assign-policies.md)か、グループに割り当てることができます。

グループに通話パーツポリシーを割り当てるには

1. [ **コールパークポリシー** ] ページの [ **グループポリシーの割り当て** ] タブで、[グループの **追加**] をクリックします。
2. 使用するグループを検索し、[ **追加**] をクリックします。
3. 他のグループ割り当てと比較して、ランクを選択します。
4. [ **ポリシーの選択**] で、このグループに割り当てるポリシーを選択します。

    ![](media/call-park-assign-policy-to-group.png)

5. [**適用**] をクリックします。

## <a name="related-topics"></a>関連トピック

[Teams で通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)

[新規-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)