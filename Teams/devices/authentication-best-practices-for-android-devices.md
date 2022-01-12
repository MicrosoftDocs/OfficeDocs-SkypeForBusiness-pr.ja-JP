---
title: Android デバイスの認証のベスト プラクティス
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Android デバイス認証を使用Teamsベスト プラクティス ガイド。
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
ms.openlocfilehash: 0ff320688d7afc583e1e806803349fb3d07ceb0c
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767210"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Android デバイスでの認証Teamsベスト プラクティス

この記事では、携帯電話や通話デバイスに認証ポリシーを展開するための一般的Teamsベスト プラクティスについて説明します。

>[!NOTE]
>条件付きアクセスには、サブスクリプションAzure Active Directory (Azure AD) プレミアムがあります。

>[!NOTE]
>Android モバイル デバイスのポリシーは、Android デバイスTeams適用されない場合があります。


## <a name="personal-and-shared-devices"></a>個人用デバイスと共有デバイス

会議室Teams共通領域の電話など、共有デバイスでは、個人のデバイスに通常適用される登録とコンプライアンスに同じ要件を使用することはできません。 共有デバイスに個人用デバイス認証要件を適用すると、次のサインインの問題が発生します。

1.  **パスワード ポリシーが原因でデバイスがサインアウトされる**

デバイスで使用Teams、パスワードの有効期限ポリシーがあります。 ユーザーとは異なり、共有デバイスで使用されるアカウントには、パスワードの有効期限が切れたときに有効な状態に更新して復元するユーザーが指定されません。 組織でパスワードの有効期限が切れ、定期的にリセットする必要がある場合、Teams 管理者がパスワードをリセットしてサインインし戻すまで、これらのアカウントは Teams デバイスで機能しなきます。

2.  **条件付きアクセス ポリシーが原因でデバイスがサインインに失敗する**

共有デバイスは、ユーザー アカウントAzure ADの条件付きアクセス ポリシーに準拠することはできません。 条件付きアクセス ポリシーのユーザー アカウントまたは個人用デバイスで共有デバイスがグループ化されている場合、サインインは失敗します。

たとえば、認証にアクセスするために多要素認証が必要Teams認証を完了するには、ユーザーの介入が必要です。 共有デバイスは多要素認証をサポートしていない。 同様に、アカウントが X 日ごとに再認証するように構成されている場合、共有デバイスはユーザーの介入なしにチャレンジを解決できません。

## <a name="best-practices-for-teams-shared-device-deployments"></a>共有デバイスのTeamsのベスト プラクティス

Microsoft では、組織のデバイスをデプロイするときにTeams設定をお勧めします。

### <a name="password-policy"></a>**パスワード ポリシー**

Teams共有デバイスでは、リソース アカウント[をExchange使用する必要があります](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 これらのアカウントは、Active Directory から同期するか、Active Directory で直接作成Azure AD。 ユーザーのパスワードの有効期限ポリシーは、共有デバイスで使用Teamsにも適用されます。

パスワードの有効期限ポリシーによる中断を回避するには、共有デバイスのパスワード有効期限ポリシーを期限切れにしないように設定します。

Teams デバイス CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams バージョン 1449/1.0.94.2021022403 for Teams phone) および[CY2021 から 更新プログラム #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams バージョン 1449/1.0.96.2021051904 for Microsoft Teams Rooms on Android)、テナント管理者は Teams デバイスにリモートでサインインできます。 デバイスをセットアップするために技術者とパスワードを共有しない。 管理者は、リモート サインインを使用して確認コードを発行し、管理センターからこれらのデバイスTeamsします。

詳細については、Android デバイスのリモート プロビジョニングとサインインに関する[ページTeams参照してください](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="conditional-access-policies"></a>**条件付きアクセス ポリシー**

Azure ADアクセスでは、サインインするためにデバイスが満たす必要がある追加の要件が設定されます。 デバイスTeams、次のガイダンスを確認して、適切なポリシーを作成したかどうかを確認します。 条件付きアクセスの概要については、「条件付きアクセス [とは」を参照してください](/azure/active-directory/conditional-access/overview)。

### <a name="multi-factor-authentication"></a>複数要素の認証

共有デバイスのアカウントは、ユーザー アカウントではなく、部屋または物理空間にリンクされます。 共有デバイスは多要素認証をサポートしないので、多要素認証ポリシーから共有デバイスを除外します。

>[!TIP]
>名前付きの場所[を使用するか、](/azure/active-directory/conditional-access/location-condition)[準拠しているデバイスを要求して](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)共有デバイスをセキュリティで保護します。

### <a name="location-based-access-with-named-locations"></a>名前付きの場所を使用した場所ベースのアクセス

共有デバイスが、IP アドレスの範囲で識別できる、定義済みの場所にプロビジョニングされている場合は、これらのデバイスの名前付き場所を使用して条件付き [アクセスを構成](/azure/active-directory/conditional-access/location-condition) できます。 この条件付きにより、これらのデバイスは、ネットワーク内にある場合にのみ、会社のリソースにアクセスできます。

### <a name="require-compliant-device"></a>準拠しているデバイスが必要

>[!NOTE]
>デバイスのコンプライアンスには Intune ライセンスが必要です。

共有デバイスを Intune に登録する場合は、条件付きアクセスのコントロールとしてデバイスコンプライアンスを構成して、準拠しているデバイスだけが会社のリソースにアクセスできるようすることができます。 Teams、デバイスのコンプライアンスに基づいて条件付きアクセス ポリシー用に構成できます。 詳細については、「条件付きアクセス: 参加しているデバイスに準拠している必要がある」[または「ハイブリッド Azure AD」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。

Intune を使用してデバイスのコンプライアンス設定を設定するには、「コンプライアンス ポリシーを使用して Intune で管理するデバイスのルールを設定する [」を参照してください](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> ホットデスクに使用されている共有デバイスは、コンプライアンス ポリシーから除外する必要があります。 コンプライアンス ポリシーは、デバイスがホットデスク ユーザー アカウントに登録されるのを防ぐためです。 代わりに、名前付きの場所を使用して、これらのデバイスをセキュリティで保護します。
> セキュリティを強化するために、名前付き[](/azure/active-directory/authentication/tutorial-enable-azure-mfa)場所ポリシーに加えて、ホットデスク ユーザーに多要素認証を要求できます。

### <a name="sign-in-frequency"></a>サインイン頻度

条件付きアクセスでは、ユーザー[](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency)が指定した期間を過ごした後にリソースにアクセスするためにもう一度サインインを要求するサインイン頻度を構成できます。 ルーム アカウントに対してサインイン頻度が適用されている場合、共有デバイスは管理者によって再びサインインされるまでサインアウトします。Microsoft では、任意のサインイン頻度ポリシーから共有デバイスを除外をお勧めします。

### <a name="filters-for-devices"></a>デバイスのフィルター

[デバイスのフィルターは](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)、条件付きアクセスの機能です。この機能を使用すると、デバイスで使用できるデバイス のプロパティに基づいて、デバイスのより詳細なポリシーをAzure AD。 デバイス オブジェクトで拡張属性 1 ~ 15 を設定し、それを使用して、独自のカスタム値を使用することもできます。

デバイスのフィルターを使用して、共通領域のデバイスを識別し、2 つの主要なシナリオでポリシーを有効にします。

1.  個人用デバイスに適用されるポリシーから共有デバイスを除外します。 たとえば、ホット デスクに使用される共有デバイスに対してデバイスのコンプライアンスを要求する必要は適用されませんが、モデル番号に基づいて他のすべてのデバイスに適用されます。

2.  個人用デバイスに適用すべきではない共有デバイスに特別なポリシーを適用する。 たとえば、これらのデバイスに設定した拡張属性 (例: "CommonAreaPhone") に基づいて、共通領域デバイスに対してポリシーとして名前付きの場所を要求します。

>[!NOTE] 
> モデル、**製造元、****および** **operatingSystemVersion** などの一部の属性は、デバイスが Intune によって管理されている場合にのみ設定できます。 デバイスが Intune によって管理されていない場合は、拡張機能属性を使用します。
