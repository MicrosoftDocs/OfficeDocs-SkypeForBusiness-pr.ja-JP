---
title: Microsoft Teams 管理センターで Skype for Business の設定を管理する
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
description: Microsoft Teams 管理センターで Skype for Business 機能の設定を管理する方法について説明します。
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834217"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Skype for Business の設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

管理者として、Microsoft Teams 管理センターでは、組織内の Skype for Business ユーザーの Skype for Business 機能を管理します。 組織 [の設定は](#manage-skype-for-business-settings-for-your-organization)**、Skype for Business** ページで管理できます [](#manage-skype-for-business-settings-for-individual-users)。また、ユーザー詳細ページの **[Skype for Business]** タブで、個々のユーザーの設定を管理できます。

Skype **for Business** ページは、組織の共存モードが Teams にのみ設定されていない場合にのみ **表示されます**。 同様に、ユーザーの共存モードが Teams のみではない場合にのみ、ユーザーの **[Skype for Business]** タブが **表示されます**。 共存モードの詳細については [、「Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) と Skype for Business の共存と相互運用性について」および「共存とアップグレードの設定」を [参照してください](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business の設定は、以前は Microsoft Teams **管理センター** のレガシ ポータルに保存されています。 従来のポータルが削除され、Skype for Business 管理用の Teams 管理センターのこれらの新しい場所に設定が移行されました。

Microsoft Teams 管理センターで Skype for Business [AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>組織の Skype for Business 設定を管理する

Microsoft Teams 管理センターの左側のナビゲーションで、組織 **全体の** 設定  >  **の Skype for Business に移動します**。 ここから、組織内のすべての Skype for Business ユーザーの Skype 会議ブロードキャスト、プレゼンス プライバシー、モバイル デバイス通知を構成および管理できます。

### <a name="skype-meeting-broadcast"></a>Skype 会議メディア

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

組織で Skype 会議ブロードキャストを [管理するには、次の](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 設定を使用します。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センターの Skype 会議ブロードキャストの設定のスクリーンショット":::

- **Skype 会議ブロードキャスト**: 組織で Skype 会議ブロードキャストを有効にするには、この機能をオンにします。 この機能を有効にした後は、Skype 会議ブロードキャスト用にネットワーク [をセットアップする必要があります](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **プレビュー機能を参照** してください:この機能をオンにすると、新機能に早期にアクセスできます。
- **開催者は匿名** の会議をスケジュールできます。組織外のユーザーがサインインすることなく参加できるブロードキャスト イベントを開催者に作成する場合は、この設定をオンにします。 
- **Skype 会議ブロードキャスト会議を記録** する: この機能をオンにして、開催者と発表者が会議を記録できます。  
- **出席者向けヘルプ** デスク サポート URL: 会議中にヘルプが必要な場合に会議出席者が使用できる組織のサポート URL を入力します。

### <a name="presence-and-mobile-notifications"></a>プレゼンスとモバイルの通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


組織の Skype for Business プレゼンス プライバシーとモバイル通知を管理するには、次の設定を使用します。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット":::

#### <a name="presence"></a>プレゼンス

既定では、組織内の Skype for Business ユーザーは、他の Skype for Business ユーザーのプレゼンス状態 (利用可能、取り込み中、または離れた場所など) を表示できます。 Skype for Business ユーザーのプレゼンスを表示できるユーザーを設定するには、次のいずれかを選択します。

- **プレゼンス情報を** 自動的に表示する: ユーザーの外部リストまたはブロックリストに追加されていない組織内のすべての Skype for  Businessユーザーは、そのユーザーのプレゼンスを表示できます。
- **ユーザー** の連絡先にのみプレゼンス情報を表示する: 外部リストまたはブロックリストに追加されていないユーザーの連絡先リスト内のすべての Skype for Businessユーザーは、そのユーザーのプレゼンスを表示できます。 ユーザーは、[設定ツール] オプションに移動して、Skype for Business の **この設定**  >  **を上書き**  >  **できます**。

#### <a name="mobile-notifications"></a>モバイルの通知

Skype for Business モバイル ユーザーが、プッシュ通知サービスを通じて、受信したインスタント メッセージ、見逃したインスタント メッセージ、ボイスメール メッセージ、および着信の着信に関する通知を受け取るかどうかを設定できます。 組織で使用されているモバイル デバイスに応じて **、Microsoft プッシュ通知サービス、Apple Push** **Notification Service、** または両方を使用できます。

以下の点について留意してください。

- プッシュ通知をオフにした場合、次回モバイル デバイスで Skype for Business を起動すると、すべての通知がユーザーに表示されます。
- 既定では、プッシュ通知はオンになっています。 個々のユーザーは、モバイル デバイスの Skype for Business でオフにできます。
- 管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。 

> [!IMPORTANT]
> マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。 このプライバシーに [関する声明をご覧ください](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>個々のユーザーの Skype for Business 設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

個々のユーザーの Skype for Business 設定を管理するには、Teams 管理センターの左側のナビゲーションで [ユーザー] に移動し、ユーザーの表示名をクリックしてユーザーの詳細ページを開き **、[Skype for Business** の設定] タブを選択します。ここから、ユーザーの外部アクセスと会議の設定を構成できます。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="ユーザーの詳細ページの Skype for Business タブのスクリーンショット":::

### <a name="external-access-settings"></a>外部アクセス設定

ユーザーが組織外のユーザーと通信できるかどうかを選択して許可またはブロックすることができます。

- **外部の Skype for Business** ユーザー: フェデレーション ドメインの Skype for Business ユーザーとの通信をユーザーに許可する場合は、この機能をオンにしてください。
- **外部の Skype ユーザー**: Skype ユーザーとの通信を許可する場合は、この機能をオンにしてください。 

### <a name="meeting-settings"></a>会議の設定

ユーザーに対して次の会議設定を構成できます。

- **オーディオ &ビデオ**: 次のいずれかのオーディオとビデオの設定を選択します。

    - **なし**: ユーザーはオーディオまたはビデオを使用することはできません。
    - **オーディオのみ**: ユーザーはオーディオを使用できますが、ビデオは使用することはできません。
    - **オーディオとビデオ**: ユーザーはオーディオとビデオを使用できます。
    - **オーディオとビデオ (HD):** ユーザーはオーディオと高解像度のビデオを使用できます。
    
- **会議中&会話** を記録する: この機能をオンにすることにより、ユーザーは会話や会議を記録できます。
- **コンプライアンス**: 電子的に保存された情報を保持するために法的に要求される場合は、この機能を有効にしてください。 
