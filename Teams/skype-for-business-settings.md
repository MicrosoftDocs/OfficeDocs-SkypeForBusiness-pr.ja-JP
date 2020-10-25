---
title: Microsoft Teams 管理センターで Skype for Business の設定を管理する
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753562"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Skype for Business の設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

管理者として、Microsoft Teams 管理センターでは、組織の Skype for business ユーザーの Skype for Business の機能を管理できます。 ユーザー詳細ページの [ **skype For business** ] タブで、[組織の](#manage-skype-for-business-settings-for-your-organization)設定を**skype for business**ページと[個々のユーザーの](#manage-skype-for-business-settings-for-individual-users)設定を管理できます。

組織の [共存] モードが [**チームのみ**] に設定されていない場合は、[ **Skype for business** ] ページのみが表示されます。 同様に、ユーザーの [共存] モードが [**チームのみ**] ではない場合は、[ **Skype for business** ] タブのみが表示されます。 共存モードの詳細については、「 [Teams と Skype For business の共存と相互運用性を理解](teams-and-skypeforbusiness-coexistence-and-interoperability.md) する」および「 [共存とアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)」を参照してください。

> [!NOTE]
> Skype for Business の設定は、以前は Microsoft Teams 管理センターの **従来のポータル** にありました。 従来のポータルが廃止されたため、Skype for Business 管理のために Teams 管理センターの新しい場所に設定が移行されました。

Microsoft Teams 管理センターで Skype for Business の機能を管理するには、グローバル管理者または Skype for Business 管理者の [AZURE AD 管理者の役割](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) が割り当てられている必要があります。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>組織の Skype for Business の設定を管理する

Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定**] の [  >  **Skype for business**] に移動します。 ここでは、組織内のすべての Skype for Business ユーザーに対して、Skype 会議ブロードキャスト、プレゼンスプライバシー、モバイルデバイス通知を構成および管理できます。

### <a name="skype-meeting-broadcast"></a>Skype 会議ブロードキャスト

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

組織の [Skype 会議ブロードキャスト](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) を管理するには、次の設定を使用します。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センターでの Skype 会議ブロードキャストの設定のスクリーンショット":::

- **Skype 会議ブロードキャスト**: これをオンにして、組織の Skype 会議ブロードキャストを有効にします。 この機能を有効にすると、 [Skype 会議ブロードキャスト用にネットワーク](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)をセットアップする必要があります。
- **「プレビュー機能」をご覧**ください。新機能をいち早く利用するには、このオプションをオンにします。
- **開催者は、匿名の会議をスケジュールでき**ます。開催者に、組織外のユーザーがサインインしなくても参加できるようにするブロードキャストイベントを作成できるようにするには、このオプションをオンにします。 
- **Skype 会議ブロードキャスト会議を記録**する: これをオンにして、開催者と発表者が会議を記録できるようにします。  
- **出席者のヘルプデスクサポート url**: 会議中にヘルプが必要な場合に、会議出席者が使用できる組織のサポート url を入力します。

### <a name="presence-and-mobile-notifications"></a>プレゼンスとモバイル通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


次の設定を使用して、組織内の Skype for Business プレゼンスプライバシーとモバイル通知を管理します。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット":::

#### <a name="presence"></a>プレゼンス

既定では、組織内の Skype for Business ユーザーは、他の Skype for Business ユーザーのプレゼンス状態 (連絡可能、取り込み中、退席中など) を表示できます。 Skype for Business ユーザーのプレゼンスを表示できるユーザーを設定するには、次のいずれかを選びます。

- **プレゼンス情報を自動的に表示**する: ユーザーの **外部** または **ブロック** されたリストに追加されていない組織内のすべての Skype for business ユーザーは、そのユーザーのプレゼンスを確認できます。
- **ユーザーの連絡先にのみプレゼンス情報を表示**する: **外部** または **ブロック** されたリストに追加されていないユーザーの連絡先リストに含まれるすべての Skype for business ユーザーは、そのユーザーのプレゼンスを確認できます。 ユーザーは、[**設定**  >  **ツール**  >  **] のオプション**に移動して、Skype for business でこの設定を上書きすることができます。

#### <a name="mobile-notifications"></a>モバイル通知

Skype for Business モバイルユーザーが、送受信されたインスタントメッセージ、ボイスメールメッセージ、不在着信について、プッシュ通知サービスを使って通知を受け取るかどうかを設定できます。 組織で使用されているモバイルデバイスに応じて、 **Microsoft プッシュ通知サービス**、 **Apple プッシュ通知サービス**、またはその両方を使用することができます。

以下の点について留意してください。

- プッシュ通知をオフにすると、ユーザーは、モバイルデバイスで Skype for Business を次に起動したときにすべての通知を受け取ります。
- 既定では、プッシュ通知はオンになっています。 各ユーザーは、モバイルデバイスの Skype for Business でそれらをオフにすることができます。
- 管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。 

> [!IMPORTANT]
> マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。 このプライバシーに関する [声明](https://go.microsoft.com/fwlink/p/?linkid=247732)を参照してください。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>個々のユーザー向けに Skype for Business の設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

個々のユーザーの Skype for Business の設定を管理するには、Teams 管理センターの左側のナビゲーションで [ **ユーザー**] に移動し、ユーザーの表示名をクリックして [ユーザーの詳細] ページを開き、[ **Skype for business の設定** ] タブを選択します。ここでは、ユーザーの外部アクセスと会議の設定を構成できます。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="[ユーザーの詳細] ページの [Skype for Business] タブのスクリーンショット":::

### <a name="external-access-settings"></a>外部アクセス設定

ユーザーが組織外のユーザーと通信できるかどうかを、選択的に許可またはブロックすることができます。

- **外部の skype For business ユーザー**: フェデレーションドメインの Skype for business ユーザーとの通信を許可する場合は、このオプションをオンにします。
- **外部の skype ユーザー**: ユーザーが skype ユーザーと通信できるようにする場合は、このオプションをオンにします。 

### <a name="meeting-settings"></a>会議の設定

ユーザーに対して次の会議の設定を構成できます。

- **オーディオ & ビデオ**: 次のいずれかのオーディオとビデオの設定を選びます。

    - **なし**: ユーザーはオーディオまたはビデオを使用できません。
    - **オーディオのみ**: ユーザーはオーディオは使用できますが、ビデオは使用できません。
    - **オーディオとビデオ**: ユーザーは音声とビデオを使用できます。
    - **オーディオとビデオ (HD)**: ユーザーはオーディオと hd のビデオを使うことができます。
    
- **会議 & の会話を記録**する: このオプションをオンにすると、ユーザーは会話と会議の記録を行うことができます。
- **コンプライアンス**: 電子的に保存された情報を保持する必要がある場合は、このオプションをオンにします。 
