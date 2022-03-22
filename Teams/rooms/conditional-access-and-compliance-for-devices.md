---
title: Microsoft Teams Rooms の条件付きアクセスとコンプライアンスのベスト プラクティス
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: お勧めの条件付きアクセスと Intune デバイスコンプライアンス ポリシーと、Microsoft Teamsについて説明します。
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689140"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms の条件付きアクセスと Intune のコンプライアンス

この記事では、共有スペースで使用される Microsoft Teams の条件付きアクセスポリシーと Intune デバイス コンプライアンス ポリシーの要件とベスト プラクティスについて説明します。

## <a name="requirements"></a>要件

Teamsアクセス ポリシーを割り当てるデバイスに会議室が既にデプロイされている必要があります。 Teams 会議室をまだデプロイしていない場合は、「会議室と共有 [Teams](with-office-365.md) デバイスのリソース アカウントを作成する」と「[Android で Microsoft Teams 会議室](../devices/collab-bar-deploy.md)をデプロイする」を参照してください。

条件付Azure Active Directoryを使用するには、P1 サービス プランを使用する必要があります。 これは、Microsoft Teams Rooms ライセンスに含まれています。

## <a name="teams-rooms-conditional-access-best-practices"></a>Teamsルームの条件付きアクセスのベスト プラクティス

条件付きアクセス ポリシーを使用すると、共有スペース内にいて、複数のユーザーが使用するデバイスでサインイン プロセスをセキュリティで保護できます。 Azure Active Directory (Azure AD) の条件付きアクセスの概要については、「Azure Active Directory? の条件付きアクセス[とは」を参照してください](/azure/active-directory/conditional-access/overview)。

条件付きアクセスを使用して会議室Teams場合は、次のベスト プラクティスを検討してください。

-   デプロイと管理を簡略化するには、Microsoft 365 Room に関連付けられているすべての Teams リソース アカウントを 1 つのユーザー グループに含めます。

-   すべての会議室リソース アカウントのTeamsを設定します。 たとえば、アカウント名は "mtr-room1@contoso.com" と "mtr-room2@contoso.com" の両方がプレフィックス "mtr-room2@contoso.com" で始まるとします。
    アカウント名が標準化されている場合は、Azure AD で動的グループを使用して、これらのすべてのアカウントに条件付きアクセス ポリシーを一度に自動的に適用できます。 動的 [グループの詳細については、「動的に設定されたグループ メンバーシップ](/azure/active-directory/enterprise-users/groups-dynamic-membership) のルール」を参照してください。

会議室でサポートされている条件付きアクセスの割り当ての一覧については、「Teams条件付きアクセス ポリシー[」を参照してください](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)。

## <a name="example-conditional-access-policy"></a>条件付きアクセス ポリシーの例

次の例では、条件付きアクセス ポリシーは次のように動作します。

1.  アカウントのサインインは、特定のユーザー グループ (この例では "共有デバイス" グループ) のメンバーである必要があります。

2.  アカウントのサインインは、オンライン、Exchange Online、Microsoft TeamsアクセスSharePoint必要があります。 他のクライアント アプリへのサインインは拒否されます。

3.  リソース アカウントは、デバイス プラットフォームでサインインWindows必要があります。

4.  リソース アカウントは、既知の信頼できる場所からサインインする必要があります。

これらの条件が正常に満たされ、ユーザーが正しいユーザー名とパスワードを入力すると、リソース アカウントは Teams。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Teams Rooms の条件付きアクセスとMicrosoft Intuneコンプライアンス

コンプライアンス要件は、オペレーティング システムの最小バージョンなど、デバイスが準拠としてマークするために満たす必要がある定義されたルールです。 デバイスは、リソース アカウントへのサインインに使用する前に、準拠しているとみなす必要があります。

Teams Rooms でサポートされている Intune コンプライアンス ポリシーの一覧については、「サポートされているデバイス コンプライアンス ポリシー[」を参照してください](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)。

Android デバイスで Intune を設定する方法の詳細Teams、Android ベースのデバイスに登録Teams [Intune の構成に関するページを参照してください](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>例 (Windowsのみ): Intune デバイスコンプライアンスを使用した条件付きアクセス

この例では、Teams の会議室Windows

1. Teams 会議室でファイアウォールが実行Windows。

2. Microsoft Defender が会議室で実行Teamsします。

3. Teams Room がこれらの要件のいずれかを満たしていない場合、準拠としてマークされません。また、デバイスはサインインしません。

このコンプライアンス ポリシーは、すべてのユーザーに適用されます。リソース アカウントTeams適用されます。
