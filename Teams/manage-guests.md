---
title: Microsoft Teams でのゲスト アクセスを管理する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 601582953136b982245bc7f4b2976c64d37424e7
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959245"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================

**ゲスト**は、Microsoft Teams のユーザー/ライセンスの種類の 1 つで、すべての Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のサブスクリプションに含まれていますす。追加の Office 365 ライセンスは必要ありません。Teams のゲスト アクセスはテナント レベルの設定であり、既定では無効になっています。ゲスト アクセスを有効にする方法について、詳しくは「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。

**ゲスト**ユーザーとライセンスの種類をオンにすると、コントロールでは、来園者に記載されている[、組織の設定をマイクロソフトのチームを管理](enable-features-office-365.md)し、[チームの管理新しいマイクロソフトのチームに移行する際の設定を構成できます。管理者センター](manage-teams-skypeforbusiness-admin-center.md)です。     
    
IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。 これらの制御は、Microsoft Teams 管理センターを介して利用可能です。 ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。

チーム所有者は、所有するチームに新しいゲストを招待したり、既存のディレクトリ ゲスト ユーザーを追加したりすることができます。チーム所有者は、ゲスト ユーザーを [**Teams**] > [**Manage teams (チームの管理)**] で識別して、そのゲストに対するチャネル関連の機能の設定を [**Org-wide settings (組織全体の設定)**] > [**Guest access (ゲスト アクセス)**] で行うことができます。この設定には、次のスクリーンショットのように、チャネルの作成、更新、削除をゲストに許可することが含まれます。

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
Azure Active Directory ポータルを使用して、ゲストの管理、および Office 365 や Teams のリソースへのゲスト アクセスの管理を行うことができます。Teams のゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。Azure Active Directory B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」および「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。

> [!NOTE]
> Microsoft Teams は、テナントへのゲスト ユーザーの追加の許可または拒否において、常に Azure Active Directory の外部設定を優先します。詳しくは、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。
  
## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>ゲスト アクセスを定期的にレビューする

Teams では、ライセンスを持っている各ユーザーごとに 5 人のゲストを追加することができます。 この制限のため、またはテナントを最新の状態に維持する必要があるため、ゲスト アクセスを定期的にレビューして、アクセスする必要がなくなったユーザーを識別する必要があります。 Azure Active Directory (Azure AD) を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。 

ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。 ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

###  <a name="prerequisites"></a>前提条件

アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。 詳細については、「[Azure Active Directory editions (Azure Active Directory のエディション)](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)」の「Choose an edition (エディションの選択)」を参照してください。 レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。 

Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加することができるゲストの合計数は、ご利用の AAD ライセンスによって許可されるものに基づきます。 詳しくは、「[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)」をご覧ください。

## <a name="guest-access-latencies"></a>ゲスト アクセスの遅延

ゲスト設定は Azure Active Directory で設定します。その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。

## <a name="more-information"></a>詳細情報

ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。


