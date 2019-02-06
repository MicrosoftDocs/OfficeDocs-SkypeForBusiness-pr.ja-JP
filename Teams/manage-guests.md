---
title: Microsoft Teams でのゲスト アクセスを管理する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef7a62f46a767271f96de6f8540867aa2e8bd917
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753611"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================

**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions. No additional Office 365 license is necessary. Teams guest access is a tenant-level setting and is turned off by default. For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).

**ゲスト**ユーザーとライセンスの種類をオンにすると、コントロールでは、来園者に記載されている[マイクロソフトのチームの管理が組織の Office 365 の機能](enable-features-office-365.md)であり、[チームの管理新しいマイクロソフトに移行する際の設定を構成できます。チーム管理センター](manage-teams-skypeforbusiness-admin-center.md)です。     
    
IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。 マイクロソフトのチーム管理センターを使用してこれらのコントロールを利用できます。 ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。

Team owners can invite new guests and add existing directory guest users to their teams. Team owners can identify guest users via **Teams** > **Manage teams**, and set channel-related capabilities for guests via **Org-wide settings** > **Guest access**, including allowing guests to create, update, and delete channels, as shown in the following screenshot.

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
You can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources. Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings. To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams always honors Azure Active Directory external settings to allow or prevent guest user additions to the tenant. For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスを外部からのアクセス (連合) との比較

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>ゲスト アクセスを定期的にレビューする

Teams では、ライセンスを持っている各ユーザーごとに 5 人のゲストを追加することができます。 この制限のため、またはテナントを最新の状態に維持する必要があるため、ゲスト アクセスを定期的にレビューして、アクセスする必要がなくなったユーザーを識別する必要があります。 Azure Active Directory (Azure AD) を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。 

ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。 ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

###  <a name="prerequisites"></a>前提条件

アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。 詳細については、「[Azure Active Directory editions (Azure Active Directory のエディション)](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)」の「Choose an edition (エディションの選択)」を参照してください。 レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。 

Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加することができるゲストの合計数は、ご利用の AAD ライセンスによって許可されるものに基づきます。 詳しくは、「[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)」をご覧ください。

## <a name="guest-access-latencies"></a>ゲスト アクセスの遅延

ゲスト設定は Azure Active Directory で設定します。 その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。 ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。

## <a name="more-information"></a>詳細情報

ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。


