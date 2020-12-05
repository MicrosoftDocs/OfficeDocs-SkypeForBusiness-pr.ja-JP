---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578400"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Skype for Business から Teams へのアップグレード &mdash; IT 管理者向け

## <a name="overview"></a>概要

Skype for Business から Teams にアップグレードする場合、一部の組織では、その組織の IT 部門によって計画と管理が実施されるプログレッシブ ロールアウトが必要になります。 このセクションの記事は、主に大規模な組織の IT 管理者を対象としています。 通常、これらの組織はオンプレミスですが、大規模な Skype for Business Online 組織の場合もあります。 これらの記事を読む前に、「 [チームのアップグレードの](upgrade-start-here.md) 概要」と「 [アップグレードフレームワークについ](upgrade-framework.md)て」を参照してください。


次の記事では、組織のアップグレードプロセスについて説明します。 

- [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [アップグレードを管理するためのツール](upgrade-to-teams-on-prem-tools.md)
- [Skype for Business オンプレミスの組織に関するその他の考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [アップグレードを実装する](upgrade-to-teams-on-prem-implement.md)
- [公衆交換電話網 (PSTN) に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。

- [Teams と Skype for Business の共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存モード-参照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>この記事では、Skype for Business Online、オンプレミスの Skype for Business Server、Skype for Business という用語を使用します。 最後の用語は、オンライン バージョンとオンプレミス バージョンの両方を指します。

作業を開始する前に、チームに移行されたユーザーが skype for business クライアントを使用しなくなったことに注意してください。ただし、Skype for Business でホストされている会議に参加することはありません。  着信したチャットや通話すべては、送信者が Teams と Skype for Business のいずれを使用しているかに関わらず、ユーザーの Teams クライアントに配信されます。 移行済みユーザーによって開催される新しい会議は、Teams 会議としてスケジュールされます。 ユーザーが Skype for Business クライアントを使用しようとすると、チャットと通話の開始がブロックされます。  ただし、ユーザーは引き続き Skype for business クライアントを使用して、招待された Skype for Business 会議に参加することができます。 (2017 年より前に出荷された以前の Skype for Business クライアントでは、TeamsUpgradePolicy は優先されません。 最新の Skype for Business クライアントを使用していることをご確認ください)。
 
[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)のプロパティである[モード](migration-interop-guidance-for-teams-with-skype.md)の概念を使って、チームへのユーザーの移行を管理します。 上で説明したように、Teams に移行されたユーザーは、"TeamsOnly" モードになります。  Teams に移行する組織の最終的な目標は、すべてのユーザーを TeamsOnly モードに移行することです。

>[!NOTE]
>Skype for Business オンプレミスアカウントを持っているユーザーは、teams のみにすることはできません。 これらのユーザーは、 [孤島モードでチームを使用](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)できますが、この方法では、Teams の唯一のモードで利用できる teams 機能一式は提供されません。 これらのユーザーをチームで使用できるようにするには、 `Move-CsUser` オンプレミスの Skype For Business Server ツールを使用してクラウドに移動する必要があります。

わかりました。 では、始めましょう。  最初のステップでは、 [利用可能なアップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)を理解しています。







   

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

