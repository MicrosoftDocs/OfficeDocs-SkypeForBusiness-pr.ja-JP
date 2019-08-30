---
title: Microsoft Teams |会議を最初に行う
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: 最初に会議について説明します。ここでは、ユーザーが Teams で会議を作成しながら、チャット、通話、プレゼンスのために Skype for Business を使い続けることができます。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68ae38caa6671b3b5b46d8f295947bdbd9527379
ms.sourcegitcommit: bb8577aca8c7e0673b37634a24bf793c86c0537b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2019
ms.locfileid: "36675537"
---
# <a name="meetings-first"></a>会議を最初に行う

"会議の最初" は、チーム会議をできるだけ迅速に使い始めることを希望しているエンタープライズ Voip オンプレミスの Skype for Business Server 組織向けに最適化されています。 このような組織では、会議を最初に行うのは、チームの会議エクスペリエンスの優先順位を指定する、**孤島**モードの代わりとなります。

## <a name="what-is-meetings-first"></a>会議とは何ですか?

会議は、最初に**SfBWithTeamsCollabAndMeetings**の共存モードに基づいています。 会議は最初は製品や機能ではありません。チームと Skype for Business の機能を利用して、独自にカスタマイズされた共存エクスペリエンスを実現する構成です。

最初に会議では、ユーザーは Teams で会議を作成しますが、チャット、通話、プレゼンスには Skype for Business を使い続けることができます。 Teams と Skype for Business の間でモダリティのオーバーラップはありません。 チャット、通話、プレゼンスは Skype for Business でオンになっており、Teams ではオフになっています。 これにより、共存時にユーザーのエクスペリエンスを強化する Skype for Business と Teams、および**チームのみ**のユーザーとの相互運用性のシナリオに、独自の "よりよい" シナリオが実現されます。

![Teams と Skype for Business を使用した、より良い組み合わせのシナリオのスクリーンショット](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 会議を最初に行うのは、アクティブなチームチャットユーザーがいない、またはほとんどない組織に適しています。 アクティブなチームチャットユーザーは、チームでチャットしたり、チャット履歴にアクセスしたりすることができなくなるため、会議の最初のモードに切り替えることはできません。 これらのユーザーは、代わりに**諸島**モードで grandfathered する必要があります。また、チーム内のチャットでまだアクティブになっていないユーザーのみに会議が許可されています。

## <a name="who-should-consider-meetings-first"></a>会議を最初に検討する必要があるユーザー

会議は最初に Skype for Business Server を使用している組織向けに設計されています。エンタープライズ Voip では、チームの会議への移行を加速する必要があります。特に、管理された明確なアップグレードパスをチームにお客様が必要としている場合。

複雑または大規模な組織では、通常、ボイスの移行はサイトごとに行われ、数年かかる場合があるため、共存シナリオが長くなります。 この共存が**孤島**モードになっている場合、ユーザーは常に2つの会議ソリューション (Skype for Business と Teams) を選ぶことができます。これにより、混乱または最適な状況が発生する可能性があります。 音声の移行とは異なり、会議の移行は通常、会社全体で短時間で完了することができます。 できるだけ早く Teams 会議に完全に切り替える (音声移行が完了するのを待たずに) 必要がある組織は、まず会議を検討する必要があります。

最初に、エンタープライズ Voip ユーザーがいない組織にとっては、会議が役に立ちません。 これらの組織は、チームの会議を導入できるようになるとすぐに、 **teams**にアップグレードすることができます。 最初に会議をスキップすることを検討してください。

さらに、会議に参加している組織では、"会議のみ" RFP が発行されている場合など、最初に会議ソリューションを使用すると便利です。

## <a name="capabilities-in-meetings-first"></a>会議の機能の先頭へ

会議を最初に行うと、次の機能が一緒に表示されます。

- [Teams の電話会議](tutorial-audio-conferencing.yml)を使って[、Skype for business Server (オンプレミス) ユーザーをプロビジョニング](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3)します。
- [会議移行サービス](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): ユーザーによって開催される会議はクラウドに移行され、ユーザーが会議に最初に昇格したとき (Exchange Online が必要)、チーム会議に変換されます。
- Teams でのユーザーエクスペリエンスが合理化され、チームの会議とチームおよびチャネルが中心となります (必要に応じて、[アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を使って非表示にすることができます)。[チームのプライベートチャット、通話、およびセルフプレゼンス](teams-client-experience-and-conformance-to-coexistence-modes.md)は会議では公開されません。これにより、展開と導入作業が会議に完全に集中できるようになります。
- チームの優れた[会議エクスペリエンス](tutorial-meetings-in-teams.yml)。
- Teams と Skype for Business の間の "組み合わせ" が向上します。 
  - 自動ホールド: Teams の会議では、Skype for Business で通話を開始すると、Teams の会議が保留になり、その逆も行われます。 これにより、ユーザーは会議の参加者が overheard のプライベートな通話を行うことができなくなります。
    ![Teams と Skype for Business を使用した、より良い組み合わせのシナリオのスクリーンショット](media/meetings-first-better-together-hold.png)
  - プレゼンス調整: Teams のアクティビティは、skype for business のチャットや通話のための Skype for Business のプレゼンスに反映されます。 具体的には、会議の最初のユーザーが Teams 会議に参加している場合は、そのことを反映するようにプレゼンスが更新されます。 ユーザーが画面を表示すると、そのプレゼンスが更新され、[応答不可] (Skype for Business の設定に基づく) が表示されます。
  - USB デバイス HID コントロールの調整 (Mac でも利用可能): HID コントロールは、Teams の会議および他のすべての状況での Skype for Business によって、Teams で受け入れられます。
  - 特に明記されていない限り、機能をさらに活用するには、最近の Windows デスクトップクライアントが必要です。

## <a name="prerequisites-for-meetings-first"></a>最初に会議の前提条件

最初に会議の唯一のハード要件は、オンプレミスの Active Directory と Skype for Business のオンプレミス展開での Teams の要件と同じです。

- 以下を含む、 [Teams の一般的な前提条件](upgrade-plan-journey-prerequisites.md)
- [Teams での id と認証](identify-models-authentication.md)
- [Teams および Skype For business 用に Azure Active Directory を構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)します。

[Skype For business ハイブリッドトポロジ](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online)は必須ではありませんが、お勧めします。 会議移行サービスや相互運用性などの一部の機能は、このトポロジに依存します。

最初に会議は、任意のバージョンの Skype for Business Server でサポートされています (サポートされていない Lync Server を使用して動作することがわかっています)。 この機能はサポートされている Skype for Business クライアントでサポートされていますが、連携機能を強化するには最新のクライアントが必要です。

これらの要件が満たされた後ではなく、 [Office 365 および Teams のライセンス](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)をユーザーに付与することができます。

初めての会議を最初に行うには、ユーザーが[Exchange Online](exchange-teams-interact.md)、 [SharePoint Online、OneDrive for Business](sharepoint-onedrive-interact.md)、および Office 365 グループの作成を有効にしている必要があります。 会議は、メールボックスがオンプレミスの Exchange 上にあるユーザー、または SharePoint Online または OneDrive For Business や Office 365 グループの作成を行っていないユーザーに対してサポートされます。 ただし、操作は完了します。 特に、オンプレミスの Exchange Server を使用している組織の場合、チームクライアントからの会議の作成と表示に関する制限、およびコンプライアンス機能に関して、いくつかの制限があります。

少なくとも、[チームのライセンス](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)をユーザーに付与する必要があります。 さらに、必要に応じて、[電話会議](set-up-audio-conferencing-in-teams.md)のライセンスを取得することもできます。

ユーザーのライセンスを付与するときに、テナントの既定として[ **Sfbonly**または**sfbwithteams sの**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)使用を許可することをお勧めします。 これにより、最初に会議を開始する準備が整う前に、ユーザーが既定の**島々**モードで自分のチームを初めて使用することがなくなります。

会議は最初に、完全なデスクトップクライアント (Windows と Mac)、ブラウザークライアント、モバイルクライアントでサポートされています。 また、 [Microsoft Teams のルーム](https://docs.microsoft.com/microsoftteams/room-systems/)との互換性もあります。 さらに簡単にするには、完全なデスクトップクライアントが必要です。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>最初に会議で Teams 会議を準備する

チーム会議で最高のエクスペリエンスをユーザーに提供するには、次のことを行う必要があります。

- 特に、「 [Microsoft Teams の会議と会議](deploy-meetings-microsoft-teams-landing-page.md)」の手順に従います。
- [環境を評価する](3-envision-evaluate-my-environment.md)。
- [Microsoft Teams 用に組織のネットワークを準備](prepare-network.md)します。
- Teams 対応の[会議室のデバイスとソリューション](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を使用して会議室をアップグレードするか、 [Microsoft Teams のクラウドビデオ相互運用機能](cloud-video-interop.md)を使用して、既存のサードパーティの会議室やデバイスが teams 会議に参加できるようにします。
- [USB オーディオデバイスとビデオデバイス](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を使って、ユーザーに対して認定されています。
- [チーム会議の認識と導入を推進](adopt-microsoft-teams-landing-page.md)するための準備を行います。
- [サービス管理を計画](4-envision-plan-my-service-management.md)します。
- 優れた[通話品質をトラブルシューティング](use-call-analytics-to-troubleshoot-poor-call-quality.md)するために、豊富な通話分析レポートについて理解しておいてください。

この段階では、中程度のサイズのプロダクション準備パイロットを実行することを検討してください。

## <a name="configure-users-for-meetings-first"></a>最初に会議のユーザーを構成する

ユーザーがライセンスを取得し、チーム会議用に組織を準備したら、最初に会議のユーザーを有効にします。 簡単になりました。1つの設定ですべてのことができます。

初めての会議のすべての機能とユーザーエクスペリエンス、ユーザーエクスペリエンスの[自動適合性](teams-client-experience-and-conformance-to-coexistence-modes.md)、会議移行サービス、および共同作業の改善によって、ユーザーを付与します (または[Microsoft Teams 管理センター](manage-teams-in-modern-portal.md)または[PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)を使用した、ユーザーのグループ、またはテナントの既定値[SfBWithTeamsCollabAndMeetings 共存モード](setting-your-coexistence-and-upgrade-settings.md)。

![会議を最初に有効にするための管理者設定のスクリーンショット](media/teams-meeting-admin-settings.png)

必要に応じて、ユーザーのチームクライアントの左側のナビゲーションからチームおよびチャネルアプリケーションを非表示にして、会議のエクスペリエンスをさらに重視します。これは、[アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を使って実現できます。

## <a name="reporting-and-call-analytics"></a>レポート作成と通話分析

会議でのチーム会議の報告と通話分析は、他のモードとは変わりません。

## <a name="related-links"></a>関連リンク

この記事を確認した後、詳細については、「[アップグレードの過程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[移行と相互運用性のガイダンス](migration-interop-guidance-for-teams-with-skype.md)」、「 [Skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。


