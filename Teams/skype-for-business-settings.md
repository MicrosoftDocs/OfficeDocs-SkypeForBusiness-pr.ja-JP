---
title: Microsoft Teams 管理センターでSkype for Business設定を管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
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
description: Microsoft Teams 管理センターでSkype for Business機能の設定を管理する方法について説明します。
ms.openlocfilehash: 26b2ba51d42a7be227b513d72add3e34f07d0fcd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269762"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでSkype for Business設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

管理者として、Microsoft Teams 管理センターは、組織内のSkype for Business ユーザーのSkype for Business機能を管理する場所です。 [組織の](#manage-skype-for-business-settings-for-your-organization)設定は、**Skype for Business** ページで管理でき、[個々のユーザーの設定は、ユーザー](#manage-skype-for-business-settings-for-individual-users)の詳細ページの **[Skype for Business**] タブで管理できます。

組織の共存モードが **Teams のみに** 設定されていない場合にのみ、**Skype for Business** ページが表示されます。 同様に、ユーザーの共存モードが **Teams 以外** の場合は、ユーザーの [**Skype for Business**] タブのみが表示されます。 共存モードの詳細については、「[Teams とSkype for Business共存と相互運用性について理解](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」と「[共存とアップグレードの設定を設定する](setting-your-coexistence-and-upgrade-settings.md)」を参照してください。

> [!NOTE]
> Skype for Business設定は、以前は Microsoft Teams 管理センターの **レガシ ポータル** にありました。 従来のポータルの廃止に伴い、Skype for Business管理のために Teams 管理センターのこれらの新しい場所に設定を移行しました。

Microsoft Teams 管理センターでSkype for Business機能を管理するには、グローバル管理者またはSkype for Business管理者の [Azure AD 管理者ロール](/azure/active-directory/roles/permissions-reference)が割り当てられている必要があります。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>組織のSkype for Business設定を管理する

Microsoft Teams 管理センターの左側のナビゲーションで、**組織全体の設定** > **Skype for Business** に移動します。 ここから、組織内のすべてのSkype for Business ユーザーに対して、Skype Meeting Broadcast、プレゼンスのプライバシー、モバイル デバイス通知を構成および管理できます。

### <a name="skype-meeting-broadcast"></a>Skype 会議メディア

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

組織内の [Skype 会議ブロードキャスト](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) を管理するには、次の設定を使用します。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理センターの Skype 会議ブロードキャスト設定のスクリーンショット。":::

- **Skype 会議ブロードキャスト**: これをオンにすると、組織の Skype 会議ブロードキャストが有効になります。 この機能を有効にした後は、 [Skype 会議ブロードキャスト用にネットワークを設定する必要があります](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **プレビュー機能を参照してください**: これをオンにすると、新機能に早期にアクセスできるようになります。
- **開催者は匿名会議をスケジュールできます**。組織外のユーザーがサインインしなくても参加できるようにするブロードキャスト イベントを開催者が作成できるようにする場合は、これをオンにします。 
- **Skype 会議ブロードキャスト会議を記録する**: これをオンにすると、開催者と発表者が会議を記録できるようになります。  
- **出席者のヘルプデスク サポート URL**: 会議中にサポートが必要な場合に会議出席者が使用できる組織のサポート URL を入力します。

### <a name="presence-and-mobile-notifications"></a>プレゼンスとモバイル通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


組織でプレゼンスのプライバシーとモバイル通知Skype for Business管理するには、次の設定を使用します。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理センターのプレゼンス設定のスクリーンショット。":::

#### <a name="presence"></a>プレゼンス

既定では、組織内のSkype for Businessユーザーは、他のSkype for Business ユーザーのプレゼンス状態 (使用可能、ビジー、退席中など) を表示できます。 次のいずれかを選択して、Skype for Business ユーザーの存在を確認できるユーザーを設定します。

- **プレゼンス情報を自動的に表示** する: ユーザーの **外部** または **ブロック** リストに追加されていない組織内のSkype for Businessユーザーは、そのユーザーのプレゼンスを確認できます。
- **ユーザーの連絡先にのみプレゼンス情報を表示する: ユーザーの連絡先** リストに追加されていないユーザーの連絡先リスト内のSkype for Businessユーザーは、そのユーザーのプレゼンスを確認できます。 ユーザーは、[設定 **ツール** > **オプション**] に移動することで、Skype for Businessでこの **設定** > をオーバーライドできます。

#### <a name="mobile-notifications"></a>モバイル通知

Skype for Businessモバイル ユーザーがプッシュ通知サービスを通じて、着信メッセージと不在着信インスタント メッセージ、ボイスメール メッセージ、不在着信に関するアラートを受け取るかどうかを設定できます。 組織で使用されているモバイル デバイスに応じて、 **Microsoft プッシュ通知サービス**、 **Apple プッシュ通知サービス**、またはその両方を使用できます。

以下の点について留意してください。

- プッシュ通知をオフにすると、ユーザーは次回モバイル デバイスでSkype for Businessを開始すると、すべてのアラートを受け取ります。
- 既定では、プッシュ通知はオンになっています。 個々のユーザーは、モバイル デバイス上のSkype for Businessで無効にすることができます。
- 管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。 

> [!IMPORTANT]
> マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。 この [プライバシーに関する声明を](https://go.microsoft.com/fwlink/p/?linkid=247732)参照してください。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>個々のユーザーのSkype for Business設定を管理する

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

個々のユーザーのSkype for Business設定を管理するには、Teams 管理センターの左側のナビゲーションで[**ユーザー**] に移動し、ユーザーの表示名をクリックしてユーザーの詳細ページを開き、**Skype for Business設定** タブを選択します。ここから、ユーザーの外部アクセスと会議の設定を構成できます。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="[ユーザーの詳細] ページの [Skype for Business] タブのスクリーンショット。":::

### <a name="external-access-settings"></a>外部アクセス設定

ユーザーが組織外のユーザーと通信できるかどうかを選択的に許可またはブロックできます。

- **外部Skype for Business ユーザー**: フェデレーション ドメイン内のSkype for Businessユーザーとの通信をユーザーに許可する場合は、これを有効にします。
- **外部 Skype ユーザー**: ユーザーが Skype ユーザーと通信できるようにする場合は、これを有効にします。 

### <a name="meeting-settings"></a>会議の設定

ユーザーに対して次の会議設定を構成できます。

- **オーディオ & ビデオ**: 次のいずれかのオーディオとビデオの設定を選択します。

    - **なし**: ユーザーはオーディオまたはビデオを使用できません。
    - **オーディオのみ**: ユーザーはオーディオを使用できますが、ビデオは使用できません。
    - **オーディオとビデオ**: ユーザーはオーディオとビデオを使用できます。
    - **オーディオとビデオ (HD)**: ユーザーは、オーディオと高解像度のビデオを使用できます。
    
- **会議&会話を記録** する: ユーザーが会話や会議を記録できるようにするには、これをオンにします。
- **コンプライアンス**: 電子的に保存された情報を保持することが法的に必要な場合は、これを有効にします。