---
title: Microsoft Teams でのゲスト アクセスを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 初めてのチームとチャネルを作成する方法、早期導入企業、使用状況とフィードバックを監視する方法、組織全体のロールアウトを計画するためのリソースを取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fea5ab9eec355d77f19165253fe97ee8aeb725ca
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139246"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================

> [!IMPORTANT]
> 変更が有効になるまで最大で 24 時間かかる場合があります。 

**ゲスト**は、Office 365 Business Premium、Office 365 Enterprise、Office 365 Business Essentials、および Office 365 Education のすべてのサブスクリプションに含まれている、Microsoft Teams のユーザーの種類です。 追加の Office 365 ライセンスは不要です。 [ゲスト アクセス ライセンス](#guest-access-licensing-limits)の詳細については、以下を参照してください。

Teams のゲスト アクセスはテナント レベルの設定であり、既定で無効になっています。 ゲスト アクセスをオンにする方法の詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照するか、[ゲスト アクセスのチェックリスト](guest-access-checklist.md)を使用してセットアップの手順をご確認ください。

ゲスト アクセスをオンにした後、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」および「[新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)」に記載されている制御を介してゲストの設定を構成することができます。     
    
IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。 これらの制御は、Teams 管理センターで利用可能です。 ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。

チーム所有者は、Teams 管理センターで自分が所有するチームに新しいゲストを招待したり、既存のディレクトリ ゲスト ユーザーを追加したりすることができます。 **[Teams]**  >  **[チームの管理]** ページでゲスト ユーザーを特定し、**[組織全体の設定]**  >  **[ゲスト アクセス]** ページでゲストに対してチャネル関連の機能を設定します。 次の図に示すように、設定には、ゲストにチャネルを作成、更新、削除することを許可することが含まれます。

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
Azure Active Directory (Azure AD) ポータルを使用して、ゲストの管理、Office 365 や Teams のリソースへのゲスト アクセスの管理を行うことができます。 Teams のゲスト アクセスでは、Azure AD ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。 Azure AD B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。

> [!NOTE]
> Microsoft Teams は、テナントへのゲスト ユーザーの追加を許可または禁止するために、常に Azure AD の外部設定を受け入れます。 詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。


## <a name="guest-access-licensing-limits"></a>ゲスト アクセス ライセンスの制限

Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加することができるゲストの合計数は、ご利用の Azure AD ライセンスによって許可されるものに基づきます。通常はライセンス ユーザーごとに 5 人です。 詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。

これらのライセンスの制限のため (およびテナントを最新の状態に維持する必要があるため)、ゲスト アクセスを定期的にレビューして、アクセスする必要がなくなったユーザーを識別する必要があります。 Azure AD を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。 

ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。 ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Azure AD アクセス レビューの前提条件

アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。 詳細については、「[Azure Active Directory のエディション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)」を参照してください。 レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>ゲスト アクセス設定が有効になるまでのラグ タイム

Azure Active Directory のゲスト アクセス設定については、変更が Office 365 組織全体に反映されるまでに 2 時間から 24 時間かかります。 ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能がオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。 ゲスト アクセスの設定の問題に関するヘルプについては、「[Teams でのゲスト アクセスのトラブルシューティング](troubleshoot-guest-access.md)」を参照してください。

  
## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細情報

ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。


