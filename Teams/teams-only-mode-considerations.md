---
title: Teams Only モードの考慮事項
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理者は、Microsoft Teams 管理センターで、Microsoft Teams 専用モードへのアップグレードを準備する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 882bb40d1d7f300f51fded6321f29bafd7f8ba92
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522500"
---
# <a name="teams-only-mode-considerations"></a>Teams Only モードの考慮事項

Office 365 組織の管理者である場合は、Microsoft Teams 管理センターで [チームのみ] モードにアップグレードするオプションが表示されるようになりました。 この機能を使用すると、個々のユーザーまたはテナント全体のどちらかをアップグレードできます。  

Teams 専用モードにアップグレードすると、ユーザーは1つのクライアントエクスペリエンスで、Office 365 のチームワークのハブである Microsoft Teams のすべてのメリットを享受できます。 さらに、チーム専用モードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかにかかわらず、すべての通話とチャットを受け取り、相互運用およびフェデレーションサポートによる恩恵を受けることができます。

多くのユーザーが Microsoft Teams にアップグレードしましたが、組織のアップグレードタイムラインとユーザーエクスペリエンスに影響を与える可能性があるという考慮事項があります。 特に、アップグレードのオプションを使用しても、組織がこの変更に対応できるというわけではありません。 最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。 

> [!IMPORTANT]
> アップグレード計画を開始する場合は、「 [Microsoft Teams のアップグレードに](upgrade-start-here.md)ついて」を参照してください。 

**共存の考慮事項**: Skype For business Online または Skype For business Server を既に使用している組織では、ニーズに合ったペースでチームを環境に導入することができます。 組織では、必要に応じて、チームを目的に応じたユーザーのセットに段階的にロールアウトできます。また、Teams を使用するユーザーは、Skype for Business を使用するユーザーと通信することができます。 このエクスペリエンスを管理するために、管理者は、エンドユーザーのクライアントエクスペリエンス、着信チャットと通話のルーティング動作、チームまたは Skype for Business で新しい会議をスケジュールするかどうかを定義する、共存モードを使用します。 ユーザーが**Teams のみ**にアップグレードされた場合、ユーザーは他の組織のユーザーとフェデレーションを行うことができます。ただし、両方のユーザーが Teams を使用する場合に最適なエクスペリエンスを提供します。 Teams にアップグレードされたユーザーのみが、引き続き Skype for Business 会議に参加できます。 

> [!NOTE]
> Teams にアップグレードされたユーザーのみが、Skype for Consumer を使っているユーザーと通信することはできません。

> [!IMPORTANT]
> 共存の詳細については、「 [Microsoft Teams と Skype For business の共存と相互運用性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)について」を参照してください。 

**テナント全体の考慮事項**: 次の環境で Teams を有効にするための作業を進めています。ただし、現在のところ、Skype for Business テナントが次のいずれかの環境でホストされている場合、管理者は組織内のユーザーをアップグレードすることはできません。

 - 21Vianet が運営する Office 365
 - Office 365 ドイツ
 - Skype for Business テナントは韓国でホストされています。**また**、組織は、韓国で Teams のデータを保存する必要があります。 現在、Skype for Business データを使用している組織では、チームにアップグレードした韓国のデータは、韓国のデータセンターの地域ではなく、アジアのデータセンターに保存されています。

**ユーザー固有の考慮事項**: 一部のユーザーシナリオはまだ進化し続けており、管理者が組織内の他のユーザーのアップグレード中に、特定のユーザーのアップグレードを一時的に延期することを決定する場合があります。 特に、プライマリデバイスが VDI ベースであるユーザーのアドレス指定のシナリオについては、引き続き取り組んでいます。 [Office 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)サイトでお知らせを監視してください。

> [!NOTE]
> Teams 専用モードに移行する前に、Teams をサポートしていないデバイスを置き換えるか更新する必要があります。 

> [!IMPORTANT]
> Teams への移行は、技術的な移行よりも多くのことを**覚えておい**てください。 アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。 Teams へのアップグレードの実装の計画の詳細については、「Skype for Business と Teams の[アップグレードのガイダンス](upgrade-framework.md)」を参照してください。  
