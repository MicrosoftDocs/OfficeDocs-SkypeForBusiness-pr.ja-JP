---
title: Microsoft Teams Roomsの条件付きアクセスとコンプライアンスのベスト プラクティス
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 推奨される条件付きアクセスとIntuneデバイス コンプライアンス ポリシーとMicrosoft Teams Roomsのベスト プラクティスについて説明します。
ms.openlocfilehash: a1d86b002a4960e58541650643574428a2c3ede5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271032"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Microsoft Teams Roomsの条件付きアクセスとIntuneコンプライアンス

この記事では、共有スペースで使用されるMicrosoft Teams Roomsの条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシーの要件とベスト プラクティスについて説明します。

## <a name="requirements"></a>要件

Teams Roomsは、条件付きアクセス ポリシーを割り当てるデバイスに既にデプロイされている必要があります。 Teams Roomsまだデプロイしていない場合は、「[会議室と共有 Teams デバイスのリソース アカウントを作成する」と](with-office-365.md) [Android でのMicrosoft Teams Roomsの展開](../devices/collab-bar-deploy.md)に関するページを参照してください。

条件付きアクセスを使用するには、Azure Active Directory P1 サービス プランが必要です。 Microsoft Teams Rooms ライセンスに含まれています。

## <a name="teams-rooms-conditional-access-best-practices"></a>条件付きアクセスのベスト プラクティスをTeams Roomsする

条件付きアクセス ポリシーは、共有スペース内にあり、複数のユーザーが使用するデバイスでサインイン プロセスをセキュリティで保護できます。 Azure Active Directory (Azure AD) の条件付きアクセスの概要については、「 [Azure Active Directory の条件付きアクセスとは?」を](/azure/active-directory/conditional-access/overview)参照してください。

条件付きアクセスを使用してTeams Roomsをセキュリティで保護する場合は、次のベスト プラクティスを検討してください。

-   展開と管理を簡略化するには、Teams Roomsに関連付けられているすべての Microsoft 365 ルーム リソース アカウントを 1 つのユーザー グループに含めます。

-   すべてのTeams Roomsリソース アカウントの名前付け標準を持ちます。 たとえば、アカウント名 'mtr-room1@contoso.com' と 'mtr-room2@contoso.com' はどちらもプレフィックス 'mrt-' で始まります。
    アカウント名が標準化されている場合は、Azure AD の動的グループを使用して、これらのすべてのアカウントに条件付きアクセス ポリシーを一度に自動的に適用できます。 [動的グループの詳細については、「動的に設定されたグループ メンバーシップの規則](/azure/active-directory/enterprise-users/groups-dynamic-membership)」を参照してください。

Teams Roomsでサポートされている条件付きアクセスの割り当ての一覧については、「[サポートされている条件付きアクセス ポリシー](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)」を参照してください。

## <a name="example-conditional-access-policy"></a>条件付きアクセス ポリシーの例

次の例では、条件付きアクセス ポリシーは次のように機能します。

1.  アカウントサインインは、特定のユーザー グループのメンバーである必要があります。この例では、"共有デバイス" グループです。

2.  サインインするアカウントは、Exchange Online、Microsoft Teams、または SharePoint Online にのみアクセスしようとしている必要があります。 他のクライアント アプリへのサインインは拒否されます。

3.  リソース アカウントは、Windows デバイス プラットフォームでサインインしている必要があります。

4.  リソース アカウントは、既知の信頼できる場所からサインインする必要もあります。

これらの条件が正常に満たされ、ユーザーが正しいユーザー名とパスワードを入力した場合、リソース アカウントは Teams にサインインします。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Teams RoomsのMicrosoft Intuneコンプライアンスを使用した条件付きアクセス

コンプライアンス要件は、オペレーティング システムの最小バージョンなど、デバイスが準拠としてマークするために満たす必要がある定義された規則です。 デバイスは、リソース アカウントへのサインインに使用する前に、準拠していると見なす必要があります。

Teams RoomsでサポートされているIntuneコンプライアンス ポリシーの一覧については、「[サポートされているデバイス コンプライアンス ポリシー](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)」を参照してください。

Teams Android デバイスでIntuneを設定する方法の詳細については、「Teams Android ベースのデバイス[を登録するためのIntuneの構成」を](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)参照してください。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>例 (Windows のみ): Intune デバイスコンプライアンスを使用した条件付きアクセス

この例では、Windows 上のTeams Rooms

1. Windows 上のTeams Roomsでファイアウォールが実行されていることを要求します。

2. Microsoft Defender がTeams Roomsで実行されていることを要求します。

3. Teams ルームがこれらの要件のいずれかを満たしていない場合は、準拠としてマークされません。デバイスはサインインしません。

このコンプライアンス ポリシーは、Teams リソース アカウントだけでなく、すべてのユーザーに適用されます。
