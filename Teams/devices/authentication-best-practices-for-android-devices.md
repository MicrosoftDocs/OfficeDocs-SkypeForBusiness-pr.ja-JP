---
title: Android デバイスの共有デバイスMicrosoft Teams認証のベスト プラクティス。
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 共有 Android デバイス管理に関するベスト Teams。 この機能は、条件付きアクセス、パスワード ポリシー、多要素認証に関するアドバイスなどです。
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279235"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Android デバイスでの共有デバイス管理Teams認証のベスト プラクティス

デバイスと一緒に使用するデバイスのTeams、さまざまなデバイス管理戦略が必要になります。 たとえば、1 人の営業担当者が使用する個人用ビジネス タブレットは、多くのカスタマー サービス担当者が共有するオンコール電話とは異なるニーズのセットを持っています。

セキュリティ管理者と運用チームは、組織内で使用できるデバイスを計画する必要があります。 各目的に *最も適* したセキュリティ対策を実装する必要があります。 この記事の推奨事項によって、これらの決定の一部が簡単になります。

>[!NOTE]
>条件付きアクセスには、Azure Active Directory (Azure AD) プレミアムがあります。

>[!NOTE]
>Android モバイル デバイスのポリシーは、Android デバイスTeams適用されない場合があります。

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>認証に関する推奨事項は、個人用と共有の Android デバイスでは異なります

共有Teamsデバイスは、個人のデバイスで使用される登録とコンプライアンスに同じ要件を使用することはできません。 個人用デバイス認証要件を共有デバイスに適用すると、サインインの問題が発生します。

1.  **デバイスは、パスワード ポリシーのためにサインアウトされます。**

デバイスで使用Teamsは、パスワードの有効期限ポリシーを持っています。 共有デバイスで使用されるアカウントには、パスワードの有効期限が切れたときに、それらを更新して動作状態に復元する特定のユーザーがありません。 組織でパスワードの有効期限が切れ、リセットする必要がある場合、Teams 管理者がパスワードをリセットしてサインインし戻すまで、これらのアカウントは Teams デバイスでの作業を停止します。

**課題**: アクセスに関しては、 Teamsからアクセスすると、ユーザーのアカウントにはパスワードの有効期限ポリシーがあります。 パスワードの有効期限が切れる場合は、パスワードを変更します。 ただし、共有デバイス ( *リソース* アカウント) で使用されるアカウントは、必要に応じてパスワードを変更できる 1 人のユーザーに接続できない可能性があります。 つまり、パスワードの有効期限が切れ、作業を再開する方法がわからずに、その場で従業員を置き去りにできます。

組織でパスワードのリセットが必要な場合、またはパスワードの有効期限が強制されている場合は、Teams 管理者がパスワードをリセットして、これらの共有アカウントがサインインし戻す準備ができている必要があります。

2.  **条件付きアクセス ポリシーが原因でデバイスがサインインに失敗する。**

**課題**: 共有デバイスは、ユーザー アカウントAzure ADの条件付きアクセス ポリシーに準拠することはできません。 条件付きアクセス ポリシーのユーザー アカウントまたは個人用デバイスで共有デバイスがグループ化されている場合、サインインは失敗 *します*。

たとえば、Teams にアクセスするために多要素認証が必要な場合は、その認証を完了するためにコードのユーザー エントリが必要です。 一般に、共有デバイスには、多要素認証を構成して完了できるユーザーは 1 人はいます。 また、アカウントが X 日ごとに再認証する必要がある場合、共有デバイスはユーザーの介入なしにチャレンジを解決できません。

多要素認証は、共有デバイスではサポートされていません。 代わりに使用するメソッドの概要を以下に示します。

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>共有 Android デバイスのデプロイに関するベスト Teams

Microsoft では、組織のデバイスをデプロイするときにTeams設定をお勧めします。

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**リソース アカウントを使用してパスワードの有効期限を抑制する**

Teams共有デバイスでは、リソース メールボックスExchange[使用する必要があります](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 これらのメールボックスを作成すると、アカウントが自動的に生成されます。 これらのアカウントは、Active Directory から同期Azure AD、または Active Directory で直接作成Azure AD。 ユーザーのパスワード有効期限ポリシーは、Teams 共有デバイスで使用されるアカウントにも適用されるため、パスワードの有効期限ポリシーによる中断を回避するには、共有デバイスのパスワード有効期限ポリシーを有効期限切れにしないように設定します。

Teams デバイス CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams バージョン 1449/1.0.94.2021022403 for Teams phone) および [CY202 1 更新プログラム #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams バージョン 1449/1.0.96.2021051904 for Microsoft Teams Rooms on Android)、テナント管理者は Teams デバイスにリモートでサインインできます。 テナント管理者は、パスワードを技術者と共有してデバイスをセットアップする代わりに、リモート サインインを使用して確認コードを発行する必要があります。 これらのデバイスのサインインは、管理センターからTeamsできます。

詳細については、Android デバイスの[リモート プロビジョニングとサインインに関するTeams参照してください](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="review-these-conditional-access-policies"></a>**これらの条件付きアクセス ポリシーを確認する**

Azure ADアクセスでは、サインインするためにデバイスが満たす必要がある追加の要件が設定されます。 デバイスTeams、次のガイダンスを確認して、共有デバイス ユーザーが自分の作業を実行できるポリシーを作成したかどうかを確認します。

> [!TIP]
> 条件付きアクセスの概要については、「条件付きアクセス [とは」を参照してください](/azure/active-directory/conditional-access/overview)。

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>共有デバイスに多要素認証を使用しない

共有デバイスのアカウントは、エンド ユーザー アカウントではなく、部屋または物理空間にリンクされます。 共有デバイスは多要素認証をサポートしないので、多要素認証ポリシーから共有デバイスを除外します。

>[!TIP]
>名前付きの場所[を使用するか、](/azure/active-directory/conditional-access/location-condition)[準拠しているデバイスを要求して](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)共有デバイスをセキュリティで保護します。

### <a name="you-can-use-location-based-access-with-named-locations"></a>名前付きの場所で場所ベースのアクセスを使用できます。

共有デバイスが、IP アドレスの範囲で識別できる、定義済みの場所にプロビジョニングされている場合は、これらのデバイスの名前付き場所を使用して条件付き [アクセスを構成](/azure/active-directory/conditional-access/location-condition) できます。 この条件付きにより、これらのデバイスは、ネットワーク内にある場合にのみ、会社のリソースにアクセスできます。

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>準拠している共有デバイスを必要としない場合

>[!NOTE]
>デバイスのコンプライアンスには Intune ライセンスが必要です。

共有デバイスを Intune に登録する場合は、条件付きアクセスのコントロールとしてデバイスコンプライアンスを構成して、準拠しているデバイスだけが会社のリソースにアクセスできるようすることができます。 Teams、デバイスのコンプライアンスに基づいて条件付きアクセス ポリシーを構成できます。 詳細については、「条件付きアクセス: 参加しているデバイスに準拠している必要がある」または[「ハイブリッド Azure AD参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。

Intune を使用してデバイスのコンプライアンス設定を設定するには、「コンプライアンス ポリシーを使用して Intune で管理するデバイスのルール [を設定する」を参照してください](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> ホット デスクに使用されている *共有デバイスは* 、コンプライアンス ポリシーから除外する必要があります。 コンプライアンス ポリシーにより、デバイスがホット デスク ユーザー アカウントに登録されるのを防ぐ。 **代わりに、名前付きの場所を使用して、これらのデバイスをセキュリティで保護します**。
> セキュリティを強化するために、名前付きの [](/azure/active-directory/authentication/tutorial-enable-azure-mfa)場所ポリシーに加えて、ホット デスク ユーザー */* ユーザー アカウントに多要素認証を要求することもできます。

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>サインイン頻度条件から共有デバイスを除外する

条件付きアクセスでは、ユーザー[](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency)が指定した期間を過ごした後にリソースにアクセスするためにもう一度サインインを要求するサインイン頻度を構成できます。 ルーム アカウントに対してサインイン頻度が適用されている場合、共有デバイスは管理者によって再びサインインされるまでサインアウトします。Microsoft では、任意のサインイン頻度ポリシーから共有デバイスを除外をお勧めします。

### <a name="using-filters-for-devices"></a>デバイスにフィルターを使用する

[デバイスのフィルターは](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)、条件付きアクセスの機能です。この機能を使用すると、デバイスで使用できるデバイス のプロパティに基づいて、デバイスのより詳細なポリシーをAzure AD。 デバイス オブジェクトで拡張属性 1 ~ 15 を設定し、それを使用して、独自のカスタム値を使用することもできます。

デバイスのフィルターを使用して、共通領域のデバイスを識別し、2 つの主要なシナリオでポリシーを有効にします。

1.  個人用デバイスに適用されるポリシーから共有デバイスを除外します。 たとえば、ホット デスクに使用される共有デバイスには、デバイスのコンプライアンスを要求する必要は適用されませんが、モデル番号に基づいて、他のすべてのデバイスに適用されます。

2.  個人用デバイスに適用すべきではない共有デバイスに *特別なポリシー* を適用する。 たとえば、これらのデバイスに設定した拡張属性 (例: "CommonAreaPhone") に基づいて、共通領域デバイスに対してポリシーとして名前付きの場所を要求します。

>[!NOTE] 
> モデル **、製造元、****operatingSystemVersion** などの一部の属性は、デバイスが Intune によって管理されている場合にのみ設定できます。  デバイスが Intune によって管理されていない場合は、拡張機能属性を使用します。
