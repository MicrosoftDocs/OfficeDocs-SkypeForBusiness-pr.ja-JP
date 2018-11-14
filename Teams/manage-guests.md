---
title: Microsoft Teams でのゲスト アクセスを管理する
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 11/13/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: rramesan
search.appverid: MET150
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 143170c6a7a174d35300b73693f0a828336b7d32
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510569"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================

**ゲスト**は、Office 365 のビジネス プレミアム、Office 365 の企業、および Office 365 の教育のすべてのサブスクリプションに含まれているマイクロソフトのチームでのユーザーとライセンスの種類です。 追加の Office 365 ライセンスは不要です。 Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。 ゲスト アクセスを有効にする方法の詳細については、[マイクロソフトのチームへのゲスト アクセスの無効を切り替える](set-up-guests.md)を参照してください。

**ゲスト**ユーザーとライセンスの種類をオンにすると、コントロールでは、来園者に記載されている[マイクロソフトのチームの管理が組織の Office 365 の機能](enable-features-office-365.md)であり、[チームの管理新しいマイクロソフトに移行する際の設定を構成できます。チームとビジネス管理センターの Skype](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。 これらの制御は Office 365 管理センターを介して利用できます。 ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。

チームの所有者では、新規来園者を招待でき、既存のディレクトリのゲスト ユーザーをチームに追加することができます。 チームの所有者が**管理チーム**では、来園者のチャネルに関連する機能を設定するさらに、 > の**ゲスト アクセス許可**を作成するには、来園者が許可されるなどの更新、および次のスクリーン ショットに示すように、チャンネルを削除します。

![チームでのゲスト アクセス権の設定です。](media/view-guests-guest-permissions.png)
  

さらに、Azure Active Directory ポータルを使用して、ゲストの管理、Office 365 や Teams のリソースへのゲスト アクセスの管理を行うことができます。 Teams のゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。 Azure Active Directory B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。
> [!NOTE]
> マイクロソフトのチームでは、Azure Active Directory 外部の設定を許可またはテナントのゲスト ユーザーの追加を禁止する常にします。 詳細については、[マイクロソフトのチームでのゲスト アクセスを許可](Teams-dependencies.md)を参照してください。
  
## <a name="guest-access-latencies"></a>ゲスト アクセスの遅延

ゲスト設定は Azure Active Directory で設定します。 その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。 ユーザーが「管理者に問い合わせてください」メッセージを表示するかどうかはゲスト機能を有効になっていないか、またはいる設定がまだ有効な可能性がありますが、自分のチームにゲストを追加しようとするとします。