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
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42910da02c55866e0ce4e04a099b60e55577ab8c
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111361"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================

> [!IMPORTANT]
> 変更が有効になるまで最大24時間かかることがあります。 

**ゲスト**は、すべての Office 365 Business Premium、Office 365 Enterprise、Office 365 Business Essentials、および Office 365 エデュケーションサブスクリプションに含まれている、Microsoft Teams のユーザーの種類です。 追加の Office 365 ライセンスは不要です。 [ゲストアクセスライセンス](#guest-access-licensing-limits)の詳細については、以下を参照してください。

Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。 ゲストアクセスを有効にする方法の詳細については、「 [Teams へのゲストアクセスを有効また](set-up-guests.md)は無効にする」を参照するか、[ゲストアクセスのチェックリスト](guest-access-checklist.md)を使用してセットアップを確認してください。

ゲストアクセスを有効にした後、「[組織のチーム設定を管理](enable-features-office-365.md)する」で説明されているコントロールを使用してゲストの設定を構成し、[新しい Microsoft Teams 管理センターへの移行中に teams を管理](manage-teams-skypeforbusiness-admin-center.md)することができます。     
    
IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。 これらのコントロールは、Teams 管理センターで使用できます。 ゲストユーザーのコンテンツとアクティビティは、Office 365 の他の部分と同じコンプライアンスおよび監査保護の対象となります。

チームの所有者は、新しいゲストを招待し、チーム管理センターで既存のディレクトリゲストユーザーを自分のチームに追加することができます。 **チーム** > **管理**ページでゲストユーザーを特定し、**組織全体** > の [**ゲストアクセス**の設定] ページでゲストのチャネル関連の機能を設定します。 [設定] には、次の図に示すように、ゲストによるチャネルの作成、更新、削除の許可が含まれます。

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
Azure Active Directory (Azure AD) ポータルを使用して、ゲストと、Office 365 および Teams リソースへのアクセスを管理することができます。 Teams ゲストアクセスでは、id プロパティ、メンバーシップ、多要素認証の設定などのセキュリティ原則情報を保存する基盤として、Azure AD のビジネス間 (B2B) コラボレーション機能を使用します。 Azure AD b2b の詳細については、「 [AZURE AD b2b コラボレーションの](https://go.microsoft.com/fwlink/p/?linkid=853011)概要」と「 [AZURE Active Directory b2b コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=853020)に関する faq」を参照してください。

> [!NOTE]
> Microsoft Teams では、ゲストユーザーによるテナントへの追加を許可または禁止するために、Azure AD の外部設定を常に使用しています。 詳細については、「 [Microsoft Teams でゲストアクセスを承認](Teams-dependencies.md)する」を参照してください。


## <a name="guest-access-licensing-limits"></a>ゲストアクセスライセンスの制限

Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加することができるゲストの合計数は、ご利用の Azure AD ライセンスによって許可されるものに基づきます。通常はライセンス ユーザーごとに 5 人です。 詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。

ライセンスの制限があるため (およびテナントを最新の状態に維持するため)、ゲストアクセスを定期的に確認して、必要のないアクセス権を持つユーザーを特定する必要があります。 Azure AD を使用して、アプリケーションに割り当てられているグループメンバーまたはユーザーのアクセスレビューを作成できます。 反復的なアクセス レビューを作成することで、時間を節約できます。 アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。 

ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。 Azure portal を使用して、ゲストアクセスレビューを実行します。 詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Azure AD access レビューの前提条件

アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。 詳細については、「 [Azure Active Directory のエディション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)」を参照してください。 レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>ゲストアクセスの設定が有効になるまでのラグタイム

Azure Active Directory のゲストアクセスの設定では、Office 365 組織全体で変更が反映されるまでに、2-24 時間がかかります。 ユーザーがチームにゲストを追加しようとしたときに、"管理者に連絡してください" というメッセージが表示される場合は、ゲスト機能が有効になっていないか、設定がまだ有効になっていない可能性があります。 ゲストアクセスの設定の問題については、「 [Teams でのゲストアクセスのトラブルシューティング](troubleshoot-guest-access.md)」を参照してください。

  
## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細情報

ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。


