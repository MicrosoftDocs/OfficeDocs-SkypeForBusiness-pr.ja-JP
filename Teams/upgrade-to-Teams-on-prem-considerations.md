---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7156c02dff45e170efde9314c15b5688fd43058
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940679"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>&mdash;IT 管理者向けの Skype For Business Server がオンプレミスの組織のアップグレードに関する考慮事項

この記事では、オンプレミスの Skype for Business Server を使用する組織に関するその他の考慮事項について説明します。 この記事は、IT 管理者向けのアップグレードの概念と実装を説明するいくつかの4つの部分です。  

- [概要](upgrade-to-teams-on-prem-overview.md)
- [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [アップグレードを管理するためのツール](upgrade-to-teams-on-prem-tools.md)
- **Skype For business オンプレミスの組織に関するその他の考慮事項** (この記事)
- [アップグレードの実装](upgrade-to-teams-on-prem-implement.md)
- [公衆交換電話網 (PSTN) に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。

- [Teams と Skype for Business の共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存モード-参照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>オンプレミスの Skype for Business Server を使用する組織に関する考慮事項

- Skype for Business Hybrid のセットアップは、TeamsOnly モードへの移行の前提条件です。 ハイブリッドを使用せずにアイランド モードで Teams を使用することは可能ですが、そのユーザーが Skype for Business オンプレミスから Skype for Business Online に移行されるまで ([Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) を使用して) は、TeamsOnly モードには移行できません。 詳細については、「[ハイブリッド接続を構成する](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。

- 組織に Skype for Business Server があり、ハイブリッド接続を設定していないが、Teams を使用してチームの機能を管理したい場合は、onmicrosoft.com ドメインを持つ管理者アカウントを使用する必要があります。 

- オンプレミスの Skype for Business アカウントを所有している Teams ユーザー (つまり、Move-CsUser を使用してクラウドにまだ移行していないユーザー) は、Skype for Business ユーザーとの相互運用や、外部ユーザーとのフェデレーションを行うことができません。 この機能は、そのユーザーがクラウドに移行した場合 (アイランド モードか TeamsOnly ユーザーとして) にのみ利用できます。 

- Skype for Business アカウントを使用しているユーザーがいる場合は、オンプレミスの Skype for Business アカウントを持つすべてのユーザーに、他のモードを明示的に割り当てない限り、チームのテナントレベルで teams Sonly モードを割り当てないでください。 

- ユーザーが適切な Skype for Business 属性を使用して Azure AD に正しく同期されていることを確認する必要があります。 これらの属性すべてには、プレフィックスとして msRTCSIP- が付きます。 ユーザーが Azure AD に正しく同期されていない場合、Teams の管理ツールでそのユーザーを管理できなくなります。 (たとえば、これらの属性を正しく同期していない場合は、オンプレミスのユーザーに Teams ポリシーを割り当てることはできません)。詳細については、「 [Teams および Skype For business 用に AZURE AD Connect を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)」を参照してください。

- ハイブリッド組織で新しい TeamsOnly ユーザーや Skype for Business Online のユーザーを作成するには、*最初にユーザーを Skype for Business Server オンプレミスで有効にしてから*、その後に、そのユーザーを Move-CsUser を使用してオンプレミスからクラウドに移行する必要があります。  最初にオンプレミスでユーザーを作成することにより、残りのオンプレミスの Skype for Business ユーザーは新しく作成されたユーザーに確実にルーティングできるようになります。 すべてのユーザーのオンラインへの移行が完了しているなら、最初にオンプレミスでユーザーを有効にする必要はありません。

- オンプレミスからクラウドにユーザーが移行されると、そのユーザーによって開催される会議は、-MoveToTeams スイッチが指定されているかどうかに基づいて、Skype for Business Online か Teams のいずれかに移行されます。

- オンプレミスのユーザーに対して Skype for Business クライアントで通知を表示する場合は、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。 オンプレミスのユーザーに関係があるのは、NotifySfbUsers パラメーターのみです。  オンプレミスのユーザーは、TeamsUpgradePolicy のオンライン インスタンスから自分のモードを受け取ります。 「[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)」のメモを参照してください。 

>[!NOTE]
> 9月3日以降に作成されたすべての新しいテナントは、組織に Skype for Business Server のオンプレミス展開が含まれていない限り2019、TeamsOnly テナントとして作成されます。 Microsoft は DNS レコードを使って、オンプレミスの Skype for Business Server 組織を特定します。 組織にパブリック DNS エントリのないオンプレミスの Skype for Business サーバーがある場合は、Microsoft サポートに連絡して、新しいテナントをダウングレードする必要があります。 



















## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

