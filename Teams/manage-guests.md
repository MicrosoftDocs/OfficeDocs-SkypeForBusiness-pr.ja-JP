---
title: Microsoft Teams でのゲスト アクセスを管理する
author: LolaJacobsen
ms.author: rramesan
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
ms.openlocfilehash: db7e67536193e53d72f2bc85bb381158d5703f17
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674498"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================

**ゲスト**は、Office 365 のビジネス プレミアム、Office 365 の企業、および Office 365 の教育のすべてのサブスクリプションに含まれているマイクロソフトのチームでのユーザーとライセンスの種類です。 追加の Office 365 ライセンスは不要です。 Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。 ゲスト アクセスを有効にする方法の詳細については、[マイクロソフトのチームへのゲスト アクセスの無効を切り替える](set-up-guests.md)を参照してください。

**ゲスト**ユーザーとライセンスの種類をオンにすると、コントロールでは、来園者に記載されている[マイクロソフトのチームの管理が組織の Office 365 の機能](enable-features-office-365.md)であり、[チームの管理新しいマイクロソフトに移行する際の設定を構成できます。チームとビジネス管理センターの Skype](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理者は、テナントのレベルでの来園者の追加、設定、およびゲスト ユーザーのポリシーとアクセス許可を管理し、プルがゲスト ユーザーの利用状況を報告します。 これらのコントロールは、マイクロソフトのチームとビジネス管理センターの Skype を使用できます。 ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。

チームの所有者では、新規来園者を招待でき、既存のディレクトリのゲスト ユーザーをチームに追加することができます。 チームの所有者は、**チーム**でのゲスト ユーザーを識別できます > **管理チーム**、および**組織全体の設定**を使用して来園者のセットのチャネルに関連する機能 > **ゲスト アクセス**、作成、更新、来園者の許可を含む、次のスクリーン ショットに示すように、チャンネルを削除します。

![チームでのゲスト アクセス権の設定](media/manage-guest-access-image1.png)
  
Azure Active Directory のポータルは、来園者と Office 365 とチームのリソースへのアクセスを管理するために使用できます。 Teams のゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。 Azure Active Directory B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。

> [!NOTE]
> マイクロソフトのチームでは、Azure Active Directory 外部の設定を許可またはテナントのゲスト ユーザーの追加を禁止する常にします。 詳細については、[マイクロソフトのチームでのゲスト アクセスを許可](Teams-dependencies.md)を参照してください。
  
## <a name="review-guest-access-periodically"></a>ゲスト アクセスを定期的に確認します。

チームでは、ライセンスを付与されたユーザーごとに 5 つのゲストを追加できます。 この制限のため、テナントを常に最新の状態に保つ必要があるため、不要になったアクセス権を持つユーザーを識別するには、定期的にゲスト アクセスを確認する必要がありますか。 Azure Active Directory (AD の Azure) を使用すると、グループのメンバーや、アプリケーションに割り当てられたユーザーに対して、アクセス確認を作成します。 作成する定期的なアクセス確認ことができます。 アプリケーションへのアクセスがあるユーザーやグループのメンバーであるユーザーを定期的に確認をする場合は、それらの確認の頻度を定義できます。 

自分でゲストのアクセス確認を実行する、独自のメンバーシップを確認するには、来園者を確認したり、アクセス確認を実行するには、アプリケーションの所有者またはビジネス意思決定者を確認できます。 ゲスト アクセス確認を実行するのにには、Azure ポータルを使用します。 詳細については、 [Azure AD のアクセス権を持つゲストのアクセス権の管理のレビュー](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)を参照してください。

###  <a name="prerequisites"></a>必要条件

アクセスのレビューは、マイクロソフトのエンタープライズ モビリティとセキュリティ、E5 に含まれる、Azure AD の P2 のプレミアム ・ エディションで使用できます。 詳細については、「 [Azure Active Directory のエディション](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)のエディションの選択」を参照してください。 レビューを作成、レビュー、フォームに記入または、アクセスを確認することによって、この機能と対話するユーザーごとにライセンスが必要です。 

独自のアクセスを確認するのには、ゲスト ユーザーに確認する場合は、ゲスト ユーザーのライセンスの詳細を表示します。 詳細については、 [Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)を参照してください。

## <a name="guest-access-latencies"></a>ゲスト アクセスの遅延

ゲスト設定は Azure Active Directory で設定します。 その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。 ユーザーが「管理者に問い合わせてください」メッセージを表示するかどうかはゲスト機能を有効になっていないか、またはいる設定がまだ有効な可能性がありますが、自分のチームにゲストを追加しようとするとします。

## <a name="more-information"></a>追加情報

PowerShell を使用してゲスト アクセスを管理する方法の詳細については、[チームへのゲスト アクセスを制御する PowerShell を使用して](guest-access-powershell.md)参照してください。


