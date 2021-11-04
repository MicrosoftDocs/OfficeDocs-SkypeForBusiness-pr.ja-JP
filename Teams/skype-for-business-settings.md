---
title: 管理Skype for Business管理センターでMicrosoft Teams設定を管理する
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 管理センターで機能の設定Skype for Business管理Microsoft Teamsします。
ms.openlocfilehash: 90748d968b2540ea6ee7e5c542623ceb0bc0fbb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767135"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>管理Skype for Business管理センターでMicrosoft Teams設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

管理者は、Microsoft Teams管理センターで、組織内Skype for Businessユーザー Skype for Business機能を管理します。 組織[の設定は](#manage-skype-for-business-settings-for-your-organization)、[Skype for Business] ページで管理し、ユーザーの詳細[](#manage-skype-for-business-settings-for-individual-users)ページの [Skype for Business] タブで個々のユーザーの設定を管理できます。

組織の共存モード **が** Skype for Business にしか設定されていない場合にのみ、Teams **表示されます**。 同様に、ユーザーの共存Skype for Businessモードが のみではない場合にのみ、ユーザーの [Teams **表示されます**。 共存モードの詳細については、「共存と相互[](teams-and-skypeforbusiness-coexistence-and-interoperability.md)運用性Teams Skype for Businessとアップグレード設定の設定」を[参照してください](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business設定は、以前は管理センターのレガシ ポータルMicrosoft Teamsでした。 レガシ ポータルの提供が取りやめ、管理のために、Teams 管理センターのこれらの新しい場所に設定Skype for Businessしました。

グローバル管理者の管理者Azure AD[](/azure/active-directory/roles/permissions-reference)ロールが割り当てられている必要があります。または、Skype for Business管理センターでSkype for Business機能を管理するには、Microsoft Teams必要があります。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>組織Skype for Business設定を管理する

管理センターの左側のナビゲーションMicrosoft Teams、[**組織全体の** 設定] に移動  >  Skype for Business。 ここから、組織内のすべてのユーザーにSkype会議ブロードキャスト、プレゼンス プライバシー、モバイル Skype for Business通知を構成および管理できます。

### <a name="skype-meeting-broadcast"></a>Skype 会議メディア

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

次の設定を使用して、組織内Skype[会議ブロードキャスト](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)を管理します。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センター Skypeブロードキャスト設定のスクリーンショット。":::

- **Skypeブロードキャストの開始**: 組織の会議ブロードキャストSkype有効にするには、この設定をオンにします。 この機能を有効にした後、会議ブロードキャスト にネットワークをSkype[する必要があります](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **「プレビュー機能:** この機能を有効にする」を参照して、新機能に早期にアクセスします。
- **開催者は匿名** 会議をスケジュールできます: 組織外のユーザーがサインインせずに参加できるブロードキャスト イベントを開催者に作成する場合は、この設定をオンにします。 
- **会議Skypeを記録する**: この機能をオンにして、開催者と発表者が会議を記録できます。  
- **出席者向けヘルプデスク** サポート URL: 会議中にヘルプが必要な場合に会議の出席者が使用できる組織のサポート URL を入力します。

### <a name="presence-and-mobile-notifications"></a>プレゼンスとモバイル通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


次の設定を使用して、組織Skype for Businessのプレゼンス プライバシーとモバイル通知を管理します。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット。":::

#### <a name="presence"></a>プレゼンス

既定では、Skype for Businessのユーザーは、他のユーザーのプレゼンス状態 ([利用可能]、[取り込み中]、または [Skype for Businessできます) を確認できます。 次のいずれかを選択して、ユーザーのプレゼンスを表示できるユーザーをSkype for Businessします。

- **プレゼンス情報を自動的** に表示する: ユーザーの [外部] または [ブロック] リストに追加されていない組織内のSkype for Business ユーザーは、そのユーザーのプレゼンスを確認できます。
- **ユーザー** の連絡先にのみプレゼンス情報を表示する: 外部リストまたはブロックリストに追加されていないユーザーの連絡先リスト内のすべての Skype for Business ユーザーは、そのユーザーのプレゼンスを表示できます。 ユーザーは、[ツール オプション] にアクセスSkype for Businessでこの設定 **設定**  >  **オーバーライド**  >  **できます**。

#### <a name="mobile-notifications"></a>モバイル通知

モバイル ユーザーが、プッシュ通知サービスをSkype for Business、インスタント メッセージ、ボイスメール メッセージ、および着信ミスに関するアラートを受信するかどうかを設定できます。 組織で使用されているモバイル デバイスに応じて **、Microsoft プッシュ通知サービス****、Apple Push Notification Service、** または両方を使用できます。

以下の点について留意してください。

- プッシュ通知をオフにした場合、ユーザーは次回モバイル デバイスで通知を開始Skype for Business通知を受け取る必要があります。
- 既定では、プッシュ通知はオンになっています。 個々のユーザーは、モバイル デバイスSkype for Businessでオフにできます。
- 管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。 

> [!IMPORTANT]
> マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。 このプライバシーに関 [する声明を参照してください](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>個々のSkype for Business設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

個々のユーザーの Skype for Business 設定を管理するには、Teams 管理センターの左側のナビゲーションで、[ユーザー] に移動し、ユーザーの表示名をクリックしてユーザーの詳細ページを開き、[Skype for Businessの設定] タブを選択します。ここから、ユーザーの外部アクセスと会議の設定を構成できます。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="ユーザーの詳細Skype for Businessタブのスクリーンショット。":::

### <a name="external-access-settings"></a>外部アクセス設定

ユーザーが組織外のユーザーと通信できるかどうかを選択的に許可またはブロックできます。

- **外部Skype for Businessユーザー**: フェデレーション ドメイン内のユーザーとの通信をユーザーに許可する場合Skype for Businessオンにする。
- **外部Skypeユーザー**: ユーザーが他のユーザーと通信できる場合は、このSkypeします。 

### <a name="meeting-settings"></a>会議の設定

ユーザーに対して次の会議設定を構成できます。

- **オーディオ & ビデオ**: 次のいずれかのオーディオとビデオの設定を選択します。

    - **なし**: ユーザーはオーディオまたはビデオを使用することはできません。
    - **オーディオのみ**: ユーザーはオーディオを使用できますが、ビデオは使用することはできません。
    - **オーディオとビデオ**: ユーザーはオーディオとビデオを使用できます。
    - **オーディオとビデオ (HD)**: ユーザーはオーディオビデオと高解像度ビデオを使用できます。
    
- **会話を&記録する**: この機能をオンにし、ユーザーが会話や会議を記録できます。
- **コンプライアンス**: 電子的に保存された情報を法的に保持する必要がある場合は、この機能を有効にしてください。