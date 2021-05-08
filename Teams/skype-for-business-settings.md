---
title: 管理Skype for Business管理センターでMicrosoft Teams設定を管理する
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 管理センターで機能の設定をSkype for Businessする方法Microsoft Teams確認します。
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117005"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>管理Skype for Business管理センターでMicrosoft Teams設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

管理者は、Microsoft Teams管理センターで、組織内Skype for Businessユーザー Skype for Business機能を管理します。 組織[の設定は](#manage-skype-for-business-settings-for-your-organization)、[Skype for Business] ページで管理できます。また、[ユーザー[](#manage-skype-for-business-settings-for-individual-users)の詳細] ページの [Skype for Business] タブで個々のユーザーの設定を管理できます。

組織の共存モード **が** Skype for Business にしか設定されていない場合にのみ、Teams **表示されます**。 同様に、ユーザーの共存Skype for Businessモードが のみではない場合にのみ、ユーザーの [Teams]**タブが表示されます**。 共存モードの詳細については、「共存と相互[](teams-and-skypeforbusiness-coexistence-and-interoperability.md)運用性TeamsとSkype for Businessとアップグレードの設定」を[参照してください](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business設定は、以前は管理センターのレ **ガシ** ポータルMicrosoft Teamsでした。 レガシ ポータルの提供が取りやめ、管理のために、Teams管理センターのこれらの新しいSkype for Businessしました。

グローバル管理者の[Azure AD 管理者](/azure/active-directory/roles/permissions-reference)ロールが割り当てられている必要があります。または、Skype for Business 管理センターでSkype for Business機能を管理するには、Microsoft Teams必要があります。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>組織Skype for Business設定を管理する

管理センターの左側のナビゲーションMicrosoft Teams、[**組織全体の** 設定] に移動  >  Skype for Business。 ここから、組織内のすべてのユーザーにSkype会議ブロードキャスト、プレゼンス プライバシー、およびモバイル Skype for Business通知を構成および管理できます。

### <a name="skype-meeting-broadcast"></a>Skype 会議メディア

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

次の設定を使用して、組織内[Skype会議ブロードキャスト](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)を管理します。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センター Skypeの会議ブロードキャスト設定のスクリーンショット":::

- **Skypeブロードキャストの開始**: 組織の会議ブロードキャストSkype有効にするには、この設定をオンにします。 この機能を有効にした後、会議ブロードキャスト にネットワークをSkype[必要があります](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **「プレビュー機能:** この機能を有効にする」を参照して、新機能に早期にアクセスします。
- **開催者は匿名** 会議をスケジュールできます: 組織外のユーザーがサインインすることなく参加できるブロードキャスト イベントを開催者に作成する場合は、この設定をオンにします。 
- **[会議Skype会議の** 記録]: 開催者と発表者が会議を記録するには、この機能をオンにしてください。  
- **出席者向け** ヘルプデスク サポート URL: 会議中にヘルプが必要な場合に会議の出席者が使用できる組織のサポート URL を入力します。

### <a name="presence-and-mobile-notifications"></a>プレゼンスとモバイル通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


組織内のプレゼンス プライバシーとモバイル通知Skype for Businessを管理するには、次の設定を使用します。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット":::

#### <a name="presence"></a>プレゼンス

既定では、Skype for Businessのユーザーは、他のユーザーのプレゼンス状態 ([利用可能]、[取り込み中]、または [Skype for Business] など) を表示できます。 次のいずれかを選択して、ユーザーのプレゼンスを表示できるユーザーをSkype for Businessします。

- **プレゼンス情報を自動的** に表示する: ユーザーの [外部] または [ブロック] リストに追加されていない組織内のSkype for Business ユーザーは、そのユーザーのプレゼンスを確認できます。
- **ユーザー** の連絡先にのみプレゼンス情報を表示する: [外部] または [ブロック] リストに追加されていないユーザーの連絡先リスト内のSkype for Businessユーザーは、そのユーザーのプレゼンスを表示できます。 ユーザーは、[ツール オプション] にアクセスSkype for Businessでこの設定 **設定**  >  **オーバーライド**  >  **できます**。

#### <a name="mobile-notifications"></a>モバイル通知

モバイル ユーザーが、プッシュ通知サービスをSkype for Business、インスタント メッセージ、ボイスメール メッセージ、および着信ミスに関するアラートを受信するかどうかを設定できます。 組織で使用されているモバイル デバイスに応じて **、Microsoft プッシュ通知サービス****、Apple Push Notification Service、** または両方を使用できます。

以下の点について留意してください。

- プッシュ通知をオフにした場合、ユーザーは次回モバイル デバイスで通知を開始Skype for Businessすべてのアラートを受け取る必要があります。
- 既定では、プッシュ通知はオンになっています。 個々のユーザーは、モバイル デバイスでSkype for Businessをオフにできます。
- 管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。 

> [!IMPORTANT]
> マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。 このプライバシーに関 [する声明を参照してください](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>個々のSkype for Business設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

個々のユーザーの Skype for Business 設定を管理するには、Teams 管理センターの左側のナビゲーションで、[ユーザー]に移動し、ユーザーの表示名をクリックしてユーザーの詳細ページを開き、[Skype for Business の設定]**タブを** 選択します。ここから、ユーザーの外部アクセスと会議の設定を構成できます。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="ユーザーの詳細Skype for Businessタブのスクリーンショット":::

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