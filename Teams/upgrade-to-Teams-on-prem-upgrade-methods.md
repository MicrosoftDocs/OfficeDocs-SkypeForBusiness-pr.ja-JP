---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515794"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>&mdash;IT 管理者向けのアップグレード方法

この記事では、Teams に移行するためのアップグレード方法について説明します。 この記事では、IT 管理者向けのアップグレードの概念と実装について説明します。  

- [概要](upgrade-to-teams-on-prem-overview.md)
- **アップグレード方法** (この記事)
- [アップグレードを管理するためのツール](upgrade-to-teams-on-prem-tools.md)
- [Skype for Business オンプレミスの組織に関するその他の考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [アップグレードの実装](upgrade-to-teams-on-prem-implement.md)
- [公衆交換電話網 (PSTN) に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。

- [Teams と Skype for Business の共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存モード-参照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>アップグレード方法

既存の組織を Skype for Business (オンラインまたはオンプレミス) から Teams にアップグレードするには、重複機能のメソッドと Select capabilities メソッドの2つの方法があります。 この記事では、お客様の組織に適した方式を選択していただく助けとして、両方の方式について概観し、それぞれの長所と短所を説明します。 

- [重複機能方式 (アイランド モードを使用)](#overlapping-capabilities-method-using-islands-mode)

   既存の Skype for Business 組織のユーザーは、移行フェーズで両方のクライアントを使用できるように、Teams に導入されています。 この期間中、これらのユーザーは Teams のほとんどの機能 (全部ではありません) を利用できます。 この構成のモードは、"アイランド" と呼ばれ、これは Skype for Business を使用する既存の組織の既定のモードです。 組織の準備ができたら、管理者はユーザーを TeamsOnly モードに移行します。

- [機能の方法の選択 (1 つ以上の Skype for Business モードを使用)](#select-capabilities-method-using-skype-for-business-modes)

   管理者は、組織内のユーザーのためのチャット、通話、および会議のスケジュール機能の移行 (Skype for Business から Teams への切り替え) を管理します。  これらの機能はいずれも、Skype for Business または Teams のいずれかで使用できますが、両方で使用することはできません。 管理者は、ユーザーのためにこの機能を Teams に移行するタイミングを制御するのに TeamsUpgradePolicy を使用します。 まだ TeamsOnly モードになっていないユーザーは、引き続き Skype for Business を使用してチャットと通話を行います。2 つのグループのユーザーは、相互運用機能を使用して通信できます。 管理者は、段階的により多くのユーザーを Teams に移行させることにより、移行を管理します。  

アップグレード方法を理解して選択したら、 [組織のチームへのアップグレードを管理するためのツール](upgrade-to-teams-on-prem-tools.md)について学習できます。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>重複機能方式 (アイランド モードを使用)

重複機能方式の場合、チャット、VoIP 通話、および会議を行うために、ユーザーは Teams と Skype for Business クライアントの両方を使用できます。 この状態は、"アイランド" モードと呼ばれます。これは、Skype for Business と Teams の通信トラフィックは (たとえ同一ユーザーのものであっても) 別々に保たれ、2 つの異なるクライアント同士が通信しないからです (同じ組織内のユーザーの場合)。 たとえば、受信者ユーザー A がアイランド モードであるとします。

- 別のユーザーの Skype for Business クライアントから開始される通信は、常にユーザー A の Skype for Business クライアントに配信されます。

- 別のユーザーの Teams クライアントから開始される通信は、*そのユーザーが同じ組織内に存在する場合*、常にユーザー A の Teams クライアントに配信されます。 

- 別のユーザーの Teams クライアントから開始される通信は、*そのユーザーがフェデレーション組織内に存在する場合*、常にユーザー A の Skype for Business クライアントに配信されます。

諸島モードは、まだ teams にアップグレードされていない既存の組織の TeamsUpgradePolicy の既定のモードです。 Microsoft 365 または Office 365 のライセンスを割り当てると、Teams と Skype for Business Online ライセンスの両方が既定で割り当てられます。 (これは、ユーザーが Skype for Business Server でオンプレミスに所属している場合でも同じです。 ユーザーの所属がオンプレミスとオンラインのいずれであっても、Teams の機能をすべて使用するには Skype for Business Online が現状では必要なため、Skype for Business Online のライセンスを有効にしたままにします)。実際、既定の構成を変更する手順をまだ何も実行していない段階でも、ユーザーは自分の組織で Teams をかなりの程度使用できます。  これは、機能のオーバーラップ方法の1つです。 この方式を採用すると、迅速かつエンドユーザー主導の導入を組織内で実現できます。

この方式が効果をもたらすには、すべてのユーザーが両方のクライアントを同時に実行している必要があります。 組織内から着信したアイランド モードのユーザー宛てのチャットと通話は、Skype for Business クライアントと Teams クライアントのいずれにも配信される可能性があり、受信者はこれを制御できません。 送信者と受信者が同じ組織内にある場合は、送信者が通信を開始するために使用するクライアントによって異なります。 送信者と受信者の組織が異なる場合、アイランド モードのユーザー宛ての着信チャットと通話は、常に Skype for Business クライアントに配信されます。  

たとえば、島のモードの受信者が Skype for Business を実行していて、Teams ではない場合、同じ組織内の他のユーザーが Teams からメッセージを送信しても、そのメッセージは表示されません (ただし最終的には、Teams でメッセージが表示されなくなったというメールが表示されます)。 同様に、ユーザーが Skype for Business を実行し、Teams を実行していない場合、他のユーザーが Skype for Business からそのユーザー宛てにメッセージを送信すると、チャットはそのユーザーに表示されません。  そのユーザーには、受け取れなかったメッセージがあることを通知するメールが送信されます。 これらのシナリオでの動作は、通話の場合も同様です。 ユーザーがどちらかのクライアントを実行していない場合、フラストレーションが生じる可能性があります。

ユーザー A がアイランド モードの場合、ユーザー A のプレゼンスは、他のユーザーからは Teams と Skype for Business とで別のものとして認識されます。

- 他のユーザーが Teams を使用している場合、ユーザー A の Teams でのアクティビティに基づくプレゼンスが表示されます。 
- 他のユーザーが Skype for Business を使用している場合、ユーザー A の Skype for Business でのアクティビティに基づくプレゼンスが表示されます。 

つまり、他のユーザーには、使用しているクライアントによって、ユーザー A の異なるプレゼンス状態が表示される可能性があります。 詳細については、「 [プレゼンス](upgrade-to-teams-on-prem-coexistence.md#presence)」を参照してください。

ユーザーを TeamsOnly モードにアップグレードする準備ができたら、ユーザーを個別にアップグレードするか、テナント全体のポリシーを使用してテナント全体を一度にアップグレードすることができます。 ユーザーが TeamsOnly モードにアップグレードされると、そのユーザーは着信したすべてのチャットと通話を Teams で受け取ります。 (Skype for Business 会議から Teams 会議への移行は、個別のユーザーに TeamsUpgradePolicy を適用した場合にのみトリガーされます。テナント単位に適用してもトリガーされません。 詳細については、「[会議の移行](upgrade-to-teams-on-prem-tools.md#meeting-migration)」を参照してください)。

ただし、アイランド モードに設定されているアップグレード済みでない受信者の場合、TeamsOnly ユーザーからのチャットと通話は、引き続き Skype for Business クライアントまたは Teams クライアントのいずれでも受信できます。  これは、Teams クライアントでは、"Teams から Teams" の通信と "Teams から Skype for Business" の通信について、たとえ同一のユーザーのものであっても、個別の会話スレッドが維持されることによります。  (「[Teams の会話 - 相互運用スレッドとネイティブ スレッド](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)」を参照してください)。たとえば、アイランド ユーザー A が Teams を使用して TeamsOnly ユーザー B にメッセージを送信するとします。ユーザー B がそのチャットに返信すると、その通信はユーザー A の Teams クライアントに配信されます。 ユーザー A が Skype for Business クライアントを使用して、ユーザー B にメッセージを送信することを前提としています。ユーザー B は Teams でチャットを受け取りますが、これは、他の会話と比較して、ユーザー b のチームクライアントで個別の会話となります。 ユーザー B がユーザー A とのこの会話に返信すると、その返信はユーザー A の Skype for Business クライアントに配信されます。 

次の表に、アイランド モードと TeamsOnly モードの両方について Teams エクスペリエンスをまとめて示します。  

| Teams エクスペリエンス | アイランド モードの場合 | TeamsOnly モードの場合 |
|:------------------ | :------------------- | :------------------ |
| 着信したチャットと通話の配信先:|  Teams または Skype for Business | Teams |
| PSTN 通話の配信先: | Skype for Business <br>(Teams での PSTN 機能の使用は、アイランド モードではサポートされていません)。    | Teams |   
 |プレゼンス  | Skype for Business と Teams のプレゼンスは独立しています。 他のユーザーが使用するクライアントによって、同一のアイランド ユーザーであっても異なる状態が表示される可能性があります。 | プレゼンスは、Teams でのユーザーのアクティビティにのみに基づきます。 他のすべてのユーザーには、使用するクライアントに関係なく、そのプレゼンスが表示されます。 | 
 | 会議のスケジュール   | 既定では、ユーザーはチームまたは Skype for Business のいずれかで会議をスケジュールできます。 ユーザーの Outlook には両方のアドインが表示されます。 |   会議のスケジュールは、Teams のみで行います。 Outlook では、Teams アドインのみを使用できます。 | 

次の表は、組織を Teams へ移行させるために重複機能方式を使用する場合のメリットとデメリットをまとめたものです。

| メリット     |       デメリット |
| :------------------ | :---------------- |
| 組織内での迅速な導入が可能になります。| 類似した機能を持つクライアントが2つあり、ユーザーインターフェイスが異なる場合は、エンドユーザーが混乱する可能性があります。 また、着信したチャットや通話の配信先クライアントをユーザーは制御できません。 |
| Skype for Business へアクセスを 100% 維持しつつ、Teams の学習と理解を深めることができます。 | ユーザーが両方のクライアントを実行していない場合に、メッセージが見つからないという理由でエンドユーザーの不満が発生する可能性があります。 メッセージが届かないという苦情がユーザーから寄せられる可能性があります。|
| 最小限の管理作業で Teams の使用を開始できます。 | 組織内のすべてのユーザーが Teams を使用していない場合、特に、すべてのユーザーが Teams でアクティブではない場合は、アイランド モードから TeamsOnly モードに移行するのが困難な場合があります。 たとえば、ユーザーの一部が TeamsOnly モードにアップグレードされると、それらのユーザーは Teams でのみ送信します。 アイランド モードの他のユーザーには、それらのメッセージは常に Teams に配信されます。 しかし、ユーザーの一部が Teams を実行していない場合、それらのメッセージは受け取れていないものとして認識されます。 |
|  | Teams を使用する場合、Skype for Business Server のオンプレミス アカウントを持つユーザーには、相互運用性やフェデレーションのサポートはありません。  このため、アイランド ユーザーの中に Skype for Business Online に所属しているユーザーと Skype for Business オンプレミスに所属しているユーザーが混在している場合、混乱を生じる可能性があります。   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>選択的機能方式 (Skype for Business の各モードを使用)

一部の組織では、組織を Skype for Business から Teams に移行する際に、シンプルで予測がより容易なエクスペリエンスをエンド ユーザーに提供することを優先する場合があります。 このモデルでは、IT 管理者は TeamsUpgradePolicy 内の Skype for Business モードのいずれかを使用して、TeamsOnly モードに移行する前に Skype for Business に残るユーザーを明示的に指定します。 管理者は、選択したユーザーを TeamsOnly モードに移行する準備ができたら、これらのユーザーのモードを TeamsOnly に更新します。 展開が進行するにつれて、Skype for Business から TeamsOnly モードへと徐々にユーザーが移行されます。  この移行中の動作は次のようになります。

- Skype for Business をまだ使用しているユーザーの場合、通信の発信元が相手側ユーザーの Teams クライアントであっても Skype for Business クライアントであっても、着信したすべてのチャットと通話は Skype for Business クライアントで受け取ります。 また、これらの Skype for Business ユーザーの場合、Teams クライアントでの通話とチャット機能は無効になり、ユーザーの混乱を防ぎ、適切なルーティングを確実に行うことができます。 

- チーム内のユーザーは、チーム、Skype for Business、または任意のフェデレーションユーザーの通信の種類に関係なく、すべての着信チャットと通話をチームクライアントで受信します。 

孤島メソッドとは異なり、select capabilities メソッドでは、Skype for Business のユーザーとチームが互いに連絡を取ることができます。 Skype for Business ユーザーと Teams ユーザーの間の通信は、相互運用性と呼ばれます。 相互運用通信は、Skype for Business のユーザーと Teams 内の別のユーザーとの間でチャットや通話を行うために、1対1の通信として使用できます。ただし、一部の高度な機能は利用できない場合があります。 (「 [相互運用性](upgrade-to-teams-on-prem-coexistence.md#interoperability)」をご覧ください。)また、招待されたユーザーはいつでも Skype for Business 会議または Teams 会議に参加できます。ただし、会議の種類に対応したクライアントを使用する必要があります。 詳細については、「[会議](upgrade-to-teams-on-prem-coexistence.md#meetings)」を参照してください。

選択機能移行のユーザーは、通常は島々のモードではないため、ユーザーのプレゼンスは、他のユーザーがどのクライアントを使用しているかに関係なく一貫しています。 ユーザーが Skype for Business モードのいずれかのモードに設定されている場合、他のすべてのユーザーに表示されるプレゼンスは、そのユーザーの Skype for Business でのアクティビティに基づきます。 同様に、ユーザーが TeamsOnly モードの場合は、他のすべてのユーザーに表示されるプレゼンスは、そのユーザーの Teams でのアクティビティに基づきます。 詳細については、「[プレゼンス](upgrade-to-teams-on-prem-coexistence.md#presence)」を参照してください。

まだ Teams を使用し始めていない組織の場合、管理者はテナント全体のモードをアイランドから SfbWithTeamsCollab に変更する必要があります。 (既に Teams を部分的に使用している組織の場合は、管理者は Teams でアクティブなユーザーを grandfather 化することにより、この変更がそれらのユーザーに適用されないようにする必要があります。 詳細について [は、「アイランドモードで Teams を既に使用している組織のための select 機能の方法](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)」を参照してください。)

モードがアイランドから SfbWithTeamsCollab に変わっても、Teams を一度も使用したことがないユーザーは、Skype for Business の使い方に違いはないように感じます。 しかし、そのユーザーが Teams を使い始めた際に利用できる機能は、チームとチャネル、およびファイルなどに限定されます。 チャット、通話、会議のスケジュールは、優先クライアントとして Skype for Business が管理者により (現在は) 指定されているため、Teams では利用できません。  

注: ユーザー A のモードがアイランドから Skype for Business のモードのいずれかに変わった場合、ユーザー A への通信を適切なクライアントにルーティングできるよう、ユーザー A と通信する他のユーザーの Teams クライアントでは、ユーザー A のモードが変更されたことが認識される必要があります。既にユーザー A との間にネイティブの "Teams から Teams" チャットを確立しているユーザーの場合、アイランドから Skype for Business のモードへのモード変更がこれらの他のユーザーの Teams クライアントで認識されるまでに、最大 36 時間がかかる場合があります。   一方、TeamsOnly モードへの既存のユーザーの変更は、他のクライアントによって 2 時間以内に検出されます。

管理者は、準備が整い次第、特定のユーザーのモードを TeamsOnly に更新することにより、そのユーザーのチャット、通話、会議のスケジュールを Teams に一度に移行できます。  

別の方法として、SfBWithTeamsCollabAndMeetings モードを使用することで、管理者はチャットと通話機能を Skype for Business に残したまま、まずは会議のスケジュールのみを Teams に移すことができます。 このモードを使用すると、ユーザーを TeamsOnly モードに移行させる準備が整っていない場合でも (既存の PSTN 機能を移行するためにさらに時間が必要である場合など)、組織は会議を Teams に移行できます。 この移行シナリオは、[Meetings First](meetings-first.md) と呼ばれます。

次の表に、TeamsOnly モードへの移行段階として Skype for Business のモードを使用する場合のメリットとデメリットをまとめて示します。


| メリット     |       デメリット |
| :------------------ | :---------------- |
| エンド ユーザーにとって予測可能なルーティングです。  すべての通話とチャットは、管理者の選択に基づき、Skype for Business または Teams のいずれかに配信されます。  | 相互運用会話では、リッチ テキスト、ファイル共有、画面共有はサポートされていません。  これはオンデマンド会議で回避できますが、同じほどシームレスではありません。  |
| 特定の機能が1つのクライアントでのみ利用可能であるため、エンドユーザーの混乱を回避します。  | 同じ機能セットについて、ユーザーは両方のクライアントを並べて試すことはできません。 これは特に、Skype for Business から Teams への移行をパラダイムの大きな変更であるとユーザーが感じている場合、考慮すべき要素となる可能性があります。 |
| Teams の段階的な導入が可能です。  |  | |
| 管理者は、Skype for Business から Teams への移行を完全に制御できます。 |  | | 
| 組織を TeamsOnly モードへ完全に移行する準備ができていない場合でも、組織は会議のために Teams を使用できます。 |  | |
| 他のユーザーに表示される特定のユーザーのプレゼンスは、使用するクライアントに関係なく同じです。  |  | |

## <a name="summary-of-upgrade-methods"></a>アップグレード方式のまとめ

次の表は、各アップグレード方式についてのまとめです。

| 重複機能 (アイランド モードを使用)     |      機能を選択する (Skype for Business モードを使用) |
| :------------------ | :---------------- |
| 着信したチャットと通話はいずれのクライアントにも配信される可能性があるため、TeamsOnly にアップグレードされる前は、ユーザーは両方のクライアントを同時に実行する必要があります。   | チャットと通話は、受信者のモードに基づき、1 つのクライアントにのみ配信されます。 アップグレード済みではないユーザーは両方のクライアントを実行することができますが、機能は重複しません (通話とチャットは Teams では利用できません)。  管理者は、ユーザーが会議のスケジュールを Teams と Skype for Business のどちらで行うかも制御できます。   |
| ユーザーは、同じ機能について、Skype for Business と Teams を併用できます。   | 管理者は、Skype for Business にも備わっているものと同じ機能を提供することなく、Teams の純粋な新機能 (チームとチャネル) をエンド ユーザーに提供できます。   |
|両方のユーザーがアイランド モードである間は、Skype for Business と Teams との間に相互運用性は生まれません。 一部のユーザーが TeamsOnly にアップグレードされると、それらのユーザーとアイランド モードのままの他のユーザーとの間に相互運用会話が発生する場合があります。 ただし、アイランド ユーザーは、Teams を使用して、相互運用会話を行わないことも選択できます。 | Skype for Business ユーザーと Teams ユーザーの間のコミュニケーションには、相互運用性が必要です。   |


## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

