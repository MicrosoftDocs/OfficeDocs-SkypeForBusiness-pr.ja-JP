---
title: Android デバイスの共有デバイス管理をMicrosoft Teamsするための認証のベスト プラクティス。
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Teamsでの共有 Android デバイス管理に関するベスト プラクティス。 条件付きアクセス、パスワード ポリシー、多要素認証のアドバイスなどが機能します。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6eef76052f662b26f946bf80839a62186c287b68
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635465"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Android デバイスでの共有デバイス管理をTeamsするための認証のベスト プラクティス

Teamsで使用されるデバイスの目標により、さまざまなデバイス管理戦略が必要になります。 たとえば、1 人の営業担当者が使用する個人用ビジネス Tablet PCには、多くの顧客サービス担当者が共有する電話とは異なる一連のニーズがあります。

セキュリティ管理者と運用チームは、組織内で使用できるデバイスを計画する必要があります。 各目的に最適な *セキュリティ* 対策を実装する必要があります。 この記事の推奨事項は、これらの決定の一部を容易にします。

>[!NOTE]
>条件付きアクセスには、Azure Active Directory (Azure AD) プレミアムサブスクリプションが必要です。

>[!NOTE]
>Android モバイル デバイスのポリシーは、Teams Android デバイスには適用されない場合があります。

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>認証に関する推奨事項は、個人用デバイスと共有 Android デバイスでは異なります

共有Teams デバイスは、個人のデバイスで使用される登録とコンプライアンスに同じ要件を使用することはできません。 個人用デバイス認証要件を共有デバイスに適用すると、サインインの問題が発生します。

1.  **デバイスは、パスワード ポリシーが原因でサインアウトされます。**

Teams デバイスで使用されるアカウントには、パスワード有効期限ポリシーがあります。 共有デバイスで使用されるアカウントには、パスワードの有効期限が切れたときに、それらを更新して動作状態に復元する特定のユーザーがいません。 組織でパスワードの期限切れとリセットが必要な場合、Teams管理者がパスワードをリセットしてサインインするまで、これらのアカウントはTeamsデバイスでの作業を停止します。

**課題**: アクセスする場合。 デバイスからTeams、ユーザーのアカウントにはパスワード有効期限ポリシーがあります。 パスワードの有効期限が切れると、パスワードは単に変更されます。 ただし、 *共有デバイス* (リソース アカウント) で使用されるアカウントは、必要に応じてパスワードを変更できる 1 人のユーザーに接続できない場合があります。 つまり、パスワードは期限切れになり、その場でワーカーを残すことができます。作業を再開する方法がわかりません。

組織でパスワードのリセットが必要な場合、またはパスワードの有効期限を強制する場合は、Teams管理者がパスワードをリセットして、これらの共有アカウントがサインインできるように準備されていることを確認します。

2.  **条件付きアクセス ポリシーが原因で、デバイスのサインインに失敗します。**

**課題**: 共有デバイスは、ユーザー アカウントまたは個人用デバイスの Azure AD 条件付きアクセス ポリシーに準拠できません。 共有デバイスが条件付きアクセス ポリシーのユーザー アカウントまたは個人用デバイスでグループ化されている場合、サインインは *失敗* します。

たとえば、Teamsにアクセスするために多要素認証が必要な場合、その認証を完了するにはコードのユーザー入力が必要です。 共有デバイスには、一般に、多要素認証を構成して完了できるユーザーは 1 人もいません。 また、アカウントが X 日ごとに再認証する必要がある場合、共有デバイスはユーザーの介入なしに課題を解決できません。

多要素認証は、共有デバイスではサポートされていません。 代わりに使用するメソッドの概要を以下に示します。

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Teamsを使用した共有 Android デバイスの展開に関するベスト プラクティス

組織内のデバイスTeams展開する場合は、次の設定をお勧めします。

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**リソース アカウントを使用し、パスワードの有効期限を制限する**

共有デバイスTeams、[Exchange リソース メールボックス](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)を使用する必要があります。 これらのメールボックスを作成すると、アカウントが自動的に生成されます。 これらのアカウントは、Active Directory から Azure AD に同期することも、Azure AD で直接作成することもできます。 ユーザーのパスワード有効期限ポリシーは、Teams共有デバイスで使用されるアカウントにも適用されるため、パスワードの有効期限ポリシーによる中断を回避するために、共有デバイスのパスワード有効期限ポリシーを無期限に設定します。

Teams デバイス CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) 以降 (Teams バージョン 1449/1.0.94.2021022403 for Teams phone) および CY2 AndroidのMicrosoft Teams Rooms用の[更新プログラム #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams バージョン 1449/1.0.96.2021051904)デバイスをリモートでTeamsします。 テナント管理者は、デバイスを設定するために技術者とパスワードを共有する代わりに、リモート サインインを使用して検証コードを発行する必要があります。 これらのデバイスのサインインは、Teams管理センターから行うことができます。

詳細については、「[Teams Android デバイスのリモート プロビジョニングとサインイン](/MicrosoftTeams/devices/remote-provision-remote-login)」を参照してください。 

### <a name="review-these-conditional-access-policies"></a>**条件付きアクセス ポリシーを確認する**

Azure AD 条件付きアクセスは、サインインするためにデバイスが満たす必要がある追加の要件を設定します。 Teams デバイスについては、次のガイダンスを確認して、共有デバイス ユーザーが作業を行えるようにするポリシーを作成したかどうかを確認します。

> [!TIP]
> 条件付きアクセスの概要については、「 [条件付きアクセスとは」](/azure/active-directory/conditional-access/overview)を参照してください。

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>共有デバイスに多要素認証を使用しない

共有デバイスのアカウントは、エンド ユーザー アカウントではなく、会議室または物理空間にリンクされます。 共有デバイスは多要素認証をサポートしていないため、多要素認証ポリシーから共有デバイスを除外します。

>[!TIP]
>共有デバイスをセキュリティで保護するには [、名前付きの場所](/azure/active-directory/conditional-access/location-condition) を使用するか [、準拠しているデバイスを必要と](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) します。

### <a name="you-can-use-location-based-access-with-named-locations"></a>名前付き場所で場所ベースのアクセスを使用できます

共有デバイスが、IP アドレスの範囲で識別できる明確に定義された場所にプロビジョニングされている場合は、これらのデバイスの [名前付き場所](/azure/active-directory/conditional-access/location-condition) を使用して条件付きアクセスを構成できます。 この条件により、これらのデバイスは、ネットワーク内にある場合にのみ、企業リソースにアクセスできるようになります。

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>準拠している共有デバイスを必要としない場合とタイミング

>[!NOTE]
>デバイス コンプライアンスには、Intune ライセンスが必要です。

共有デバイスをIntuneに登録する場合は、コンプライアンスに準拠しているデバイスのみが会社のリソースにアクセスできるように、条件付きアクセスのコントロールとしてデバイスコンプライアンスを構成できます。 Teamsデバイスは、デバイスコンプライアンスに基づいて条件付きアクセス ポリシー用に構成できます。 詳細については、「 [条件付きアクセス: 準拠またはハイブリッドの Azure AD 参加済みデバイスを必要とする](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)」を参照してください。

Intuneを使用してデバイスのコンプライアンス設定を設定するには、「[コンプライアンス ポリシーを使用して、Intuneで管理するデバイスのルールを設定](/intune/protect/device-compliance-get-started)する」を参照してください。

>[!NOTE]
> *ホット デスク* に使用されている共有デバイスは、コンプライアンス ポリシーから除外する必要があります。 コンプライアンス ポリシーは、デバイスがホット デスク ユーザー アカウントに登録されないようにします。 **代わりに、名前付き場所を使用して、これらのデバイスをセキュリティで保護します**。
> セキュリティを強化するために、名前付き場所ポリシーに加えて *、ホット デスクユーザー/ユーザー アカウント* に [多要素認証を要求](/azure/active-directory/authentication/tutorial-enable-azure-mfa)することもできます。

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>サインイン頻度条件から共有デバイスを除外する

条件付きアクセスでは、ユーザーが指定した期間後にリソースにアクセスするためにもう一度サインインするようにサインイン [頻度を構成](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) できます。 ルーム アカウントに対してサインイン頻度が適用されている場合、共有デバイスは管理者が再度サインインするまでサインアウトします。Microsoft では、サインイン頻度ポリシーから共有デバイスを除外することをお勧めします。

### <a name="using-filters-for-devices"></a>デバイスにフィルターを使用する

[デバイスのフィルター](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) は条件付きアクセスの機能であり、Azure AD で使用可能なデバイスのプロパティに基づいて、デバイスのより詳細なポリシーを構成できます。 また、デバイス オブジェクトに拡張属性 1 ~ 15 を設定し、それらを使用して、独自のカスタム値を使用することもできます。

デバイスのフィルターを使用して共通領域デバイスを識別し、2 つの主要なシナリオでポリシーを有効にします。

1.  個人用デバイスに適用されたポリシーから共有デバイスを除外する。 たとえば、ホット デスクに使用される共有デバイスにはデバイス コンプライアンスの要求は *適用されません* が、モデル番号に基づいて他のすべてのデバイスに *適用されます* 。

2.  個人用デバイスに適用 *すべきでない* 共有デバイスに対して特別なポリシーを適用する。 たとえば、これらのデバイスに設定した拡張属性に基づいて、共通領域デバイスに対してのみ名前付き場所をポリシーとして要求します (例: "CommonAreaPhone")。

>[!NOTE] 
> **モデル**、**製造元**、**operatingSystemVersion** などの一部の属性は、デバイスがIntuneによって管理されている場合にのみ設定できます。 デバイスがIntuneによって管理されていない場合は、拡張機能属性を使用します。
