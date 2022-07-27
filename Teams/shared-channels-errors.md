---
title: Microsoft Teams の共有チャネル エラー
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Microsoft Teams の共有チャネルで修正エラーを使用する方法について説明します。
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024164"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Microsoft Teams の共有チャネル エラー

組織外のユーザーを共有チャネルに追加しようとしたときにユーザーにエラー メッセージが表示される場合は、この記事の設定を確認してください。 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>管理者ポリシーのため、外部ユーザーをチャネルに追加することはできません。 詳細については、管理者にお問い合わせください。

Teams では、チーム メンバーシップにMicrosoft 365 グループを使用します。 組織外のユーザーを共有チャネルに追加するには、Microsoft 365 グループゲスト設定をオンにする必要があります。 ユーザーにこのエラーが表示される場合は、組織外のユーザーのMicrosoft 365 グループ設定を確認します。

組織外のユーザーのMicrosoft 365 グループ設定を設定するには
1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[**設定] を** 展開します。
1. [ **組織の設定]** をクリックします。
1. 一覧で [**Microsoft 365 グループ**] をクリックします。
1. [**グループ所有者が組織外のユーザーをゲストとしてMicrosoft 365 グループに追加** できるようにする] チェック ボックスと [**ゲスト グループ メンバーがグループ コンテンツにアクセスできるようにする**] チェック ボックスの両方がオンになっていることを確認します。
1. 変更を加えた場合は、[ **変更の保存]** をクリックします。

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>管理者ポリシーのため、外部ユーザーをチャネルに追加することはできません

Teams チャネル ポリシーは、ユーザーが共有チャネルと対話する方法を決定します。 ユーザーにこのエラー メッセージが表示される場合は、そのユーザーのチャネル ポリシーを確認します。

組織外のユーザーを共有チャネルに招待するためのポリシーを設定するには
1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams > Teams ポリシーに移動します。
1. ユーザーが割り当てられているポリシーを選択します。
1. **[共有チャネルに外部ユーザーを招待する]** が **[オン]** になっていることを確認します。
1. 変更を加えた場合は、[適用] を選択 **します**。

Teams チャネル ポリシーの詳細については、「 [Microsoft Teams でチャネル ポリシーを管理する」を参照してください](teams-policies.md)。

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>このチャネルをこの組織のユーザーと共有することはできません

ユーザーにこのエラーが表示された場合、Azure Active Directory クロステナント アクセス設定によって、他の組織のユーザーとチャネルを共有できなくなります。 これは、組織内の受信設定または他の組織の送信設定が原因である可能性があります。

組織の受信設定を確認するには
1. [Azure Active Directory](https://aad.portal.azure.com) で [**外部 ID] を** 選択し、**クロステナント アクセス設定** を選択します。
1. 確認する組織の受信アクセス リンクを選択します。
1. **[B2B 直接接続**] タブで、[**設定のカスタマイズ**] を選択します。
1. [ **外部ユーザーとグループ** ] タブで、[ **アクセスを許可する** ] と [ **すべての外部ユーザーとグループ** ] が選択されているか、[ **外部ユーザーとグループの選択]** を選択した場合は、招待されるユーザーが選択したグループのメンバーであることを確認します。
1. 変更を加えた場合は、[ **保存]** を選択し、[ **受信アクセス設定]** ブレードを閉じます。

ユーザーに引き続きエラーが表示される場合は、共同作業している組織に問い合わせてください。 その組織の送信設定により、組織との共有が禁止される場合があります。 組織間で共有チャネルを設定する方法については、「共有 [チャネル内の外部参加者と共同作業する](/microsoft-365/solutions/collaborate-teams-direct-connect)」を参照してください。

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>一致する項目が見つかりませんでした。 メール アドレスが正しいことを確認するか、管理者に問い合わせてください

ユーザーにこのエラーが表示された場合、Microsoft 365 は外部組織で指定された電子メール アドレスを見つけることができません。 アドレスを外部組織に確認する必要があります。

