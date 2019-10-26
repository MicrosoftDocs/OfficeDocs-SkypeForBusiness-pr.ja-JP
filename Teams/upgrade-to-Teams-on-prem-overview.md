---
title: Skype for Business オンプレミス展開から Teams にアップグレードする-Microsoft Teams
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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef0a06ceb37cdfff3e9e4952f10397e7ee9b698
ms.sourcegitcommit: 876b576db1fee38c09ab3a0092116212e498eda7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "37733129"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Skype for Business から IT 管理者&mdash;向けの Teams にアップグレードする

## <a name="overview"></a>概要

Skype for Business から Teams にアップグレードする場合、組織によっては、IT 部門によって計画および管理される段階的なロールアウトが必要になります。 この記事は、主に大企業のオンプレミスの組織の IT 管理者を対象としていますが、一部の Skype for Business Online 組織にも適用されることがあります。  この記事を読む前に、「[チームのアップグレードの](upgrade-start-here.md)概要」と「[アップグレードフレームワークについ](upgrade-framework.md)て」を参照してください。

>[!NOTE]
>この記事では、「Skype for Business Online」、「Skype for Business オンプレミス」、「Skype for Business」という用語を使用します。  後者の用語は、オンラインとオンプレミスの両方のバージョンを指します。

チームに移行されたユーザーが、skype for business クライアントを使用しなくなりました。ただし、Skype for Business でホストされている会議に参加することはありません。  送信者が Teams または Skype for Business を使用しているかどうかに関係なく、ユーザーのチームクライアントですべての着信チャットと通話ができます。 移行したユーザーが開催した新しい会議は、Teams 会議としてスケジュールされます。 ユーザーが Skype for Business クライアントを使用しようとすると、チャットの開始と通話<sup>はブロックされます</sup>。  ただし、ユーザーは引き続き Skype for Business クライアントを使用して、招待された会議に参加することができます。
 
管理者は、 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)のプロパティである[モード](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)の概念を使って、チームへの切り替えを管理します。 上で説明したように、Teams に移行されたユーザーは、"TeamsOnly" モードになります。  チームに移行する組織の場合、最終的な目標は、すべてのユーザーを Teams Sonly モードに移行することです。

既存の組織を Skype for Business (オンラインまたはオンプレミス) のチームに移行するには、次の2つの方法があります。

- **Side-by-side 方法**(孤島モードを使用): 既存の Skype for business 組織内のユーザーは、移行フェーズで両方のクライアントを並べて使用できるように、チームに導入されています。 この期間中は、チームのすべての機能ではなく、ほとんどすべての機能を利用できます。 この構成のモードは、"孤島" と呼ばれます。これは、Skype for Business を使用する既存の組織の既定のモードです。 組織の準備ができたら、管理者はユーザーを teams Sonly モードに移行します。

- **管理者**が、組織内のユーザーのためのチャット、通話、および会議のスケジュール機能を使って、移行 (Skype for Business から Teams への切り替え) を管理します。  これらの関数は、いずれも Skype for Business または Teams で利用できますが、両方を使用することはできません。 管理者は、TeamsUpgradePolicy を使用して、この機能をユーザーのチームに移行するタイミングを制御します。 まだ TeamsOnly モードになっていないユーザーは、引き続き Skype for Business を使用してチャットや通話を行うことができます。また、2つのユーザーを相互運用機能で通信することができます。 管理者は、より多くのユーザーを TeamsOnly モードに段階的に移行することで、切り替えを管理します。  

この記事では、両方の方法について説明し、それぞれの長所と短所を提示して、組織に適した方法を選択する方法について説明します。 

**注:**
2017 前に出荷され<sup>た従来の</sup>Skype for business クライアントは、TeamsUpgradePolicy を使用できません。 最新の Skype for Business クライアントを使用していることを確認します。


## <a name="side-by-side-method-using-islands-mode"></a>Side-by-side 方法 (孤島モードを使用)

並列方式を使うと、ユーザーはチームと Skype for Business クライアントの両方を使用してチャット、VoIP 通話、会議を行うことができます。 この状態は、Skype for Business と Teams の通信トラフィックが別々に (同じユーザーに対しても) 維持され、2つの異なるクライアントが相互に通信できないため (同じ組織内のユーザーの場合)、"孤島" モードと呼ばれます。 たとえば、受信者のユーザー A が諸島モードであるとします。

- 別のユーザーの Skype for business クライアントから開始された通信は、ユーザー A の Skype for business クライアントに常に着陸します。
- 他のユーザーのチームクライアントから開始された通信は、*他のユーザーが同じ組織内にいる場合*に、ユーザー A のチームクライアントに常に着陸します。 
- 他のユーザーのチームクライアントから開始された通信は、*他のユーザーがフェデレーション組織内にいる場合*に、ユーザー A の Skype for business クライアントに常に着陸します。

諸島モードは、まだ teams ではない既存の組織の TeamsUpgradePolicy の既定のモードです。 Office 365 ライセンスを割り当てると、Teams と Skype for Business Online ライセンスの両方が既定で割り当てられます。<sup>2</sup>実際には、既定の構成を変更する手順を実行していない場合は、既に組織内の Teams が使用されている可能性があります。  これは、並列アプローチの長所の1つです。 組織内での迅速なエンドユーザーによる導入を可能にします。

この方法で効率的に作業するには、すべてのユーザーが両方のクライアントを同時に実行する必要があります。 組織内のユーザーとの間でのチャットや通話の着信は、Skype for Business または Teams クライアントのどちらかに着陸できます。これは、受信者の管理下にありません。 これは、送信者が通信を開始するために使用するクライアントによって異なります。 送信者と受信者が異なる組織にある場合は、諸島モードでのユーザーへの通話とチャットの着信が常に Skype for Business クライアントに着陸します。  

たとえば、諸島モードの受信者が Skype for Business を実行していて、Teams からのメッセージを他のユーザーが実行している場合、その部署のモードの受信者にはメッセージが表示されません (ただし、最終的には Teams のメッセージが表示されなくなったというメールが届きます)。 同様に、ユーザーがチームを実行していても、Skype for business を使っていない場合、そのユーザーが Skype for Business からのメッセージを受け取った場合、そのチャットは表示されません。  不在着信メッセージがあったことを知らせるメールが送信されます。 各ケースの動作は、通話の場合と似ています。 ユーザーが両方のクライアントを実行しない場合は、簡単に不満を招く可能性があります。

ユーザー A が諸島モードになっている場合、Teams と Skype for Business の他のユーザーに表示されるユーザー A のプレゼンスは、次のように独立しています。

- 他のユーザーが Teams を使用すると、Teams でのユーザーのアクティビティに基づいてプレゼンスが表示されます。 
- Skype for Business を使用している場合、他のユーザーには、Skype for Business でのユーザーのアクティビティに基づいてプレゼンスが表示されます。 

これにより、他のユーザーは、使用しているクライアントに応じて、ユーザー A に異なるプレゼンス状態が表示されることがあります。 詳細については、「[プレゼンス](#presence)」を参照してください。

ユーザーを TeamsOnly モードにアップグレードする準備ができたら、ユーザーを個別にアップグレードするか、テナント全体のポリシー<sup>3</sup>を使用してテナント全体を一度にアップグレードできます。 ユーザーが TeamsOnly モードにアップグレードされると、チーム内のすべての着信チャットと通話が受信されます。 

ただし、島々モードでアップグレードされていない受信者は、Skype for Business または Teams クライアントで、TeamsOnly ユーザーからのチャットや通話を引き続き受信する可能性があります。  これは、チームのクライアントが、同じユーザーに対してもチーム間とチーム間の通信スレッドの個別の会話スレッドを保持しているためです。  (「[チームの会話」と「ネイティブスレッド」を](#teams-conversations---interop-versus-native-threads)ご覧ください)。 たとえば、島々ユーザー A が Teams を使用して、ユーザー B にメッセージを表示するとします。ユーザー B がそのチャットに返信した場合、コミュニケーションはユーザー A の Teams クライアントに表示されます。 ユーザー A が Skype for Business クライアントを使用して、ユーザー B にメッセージを送信することを前提としています。ユーザー B は Teams でチャットを受け取りますが、これは、他の会話と比較して、ユーザー b のチームクライアントで個別の会話となります。 ユーザー B がユーザー A とこの会話に返信した場合、ユーザー A の Skype for Business クライアントに表示されます。 

次の表は、島々モードと TeamsOnly モードの両方の Teams エクスペリエンスをまとめたものです。  

| Teams のエクスペリエンス | 諸島モードの場合 | TeamsOnly モードの場合 |
|:------------------ | :------------------- | :------------------ |
| 受信したチャットと通話:|  Teams または Skype for Business | Teams |
| 受信した PSTN 通話: | Skype for Business <br>(Teams での PSTN 機能の使用は、諸島モードではサポートされていません)。    | Teams |   
 |プレゼンス  | Skype for Business および Teams のプレゼンスは、独立しています。 ユーザーが使用しているクライアントによって、同じ島々ユーザーに対して異なる状態が表示されることがあります。 | プレゼンスは、Teams でのユーザーのアクティビティにのみ基づいています。 他のすべてのユーザー (使用しているクライアントに関係なく) は、そのプレゼンスを確認してください。 | 
 | 会議のスケジュール   | ユーザーは、チームまたは Skype for Business で会議をスケジュールできます。 Outlook で両方のアドインが表示されます。 |   ユーザーは Teams でのみ会議をスケジュールします。 Teams アドインのみが Outlook で利用できます。 | 

次の表では、組織をチームに移行するために並列方式を使用する場合の長所と短所について説明します。

| 担当     |       面 |
| :------------------ | :---------------- |
| 組織内での迅速な導入を可能にします。| 類似した機能を持つ2つのクライアントがあり、ユーザーインターフェイスが異なるため、エンドユーザーが混乱する可能性があります。 また、通話の発信先のクライアントを管理することもできません。 |
| ユーザーは、Skype for Business へのフルアクセスを保持しながら、チームについて学習し、理解を深めることができます。 | ユーザーが両方のクライアントを実行していない場合に、メッセージが見つからないという理由でエンドユーザーの不満が発生する可能性があります。 ユーザーがメッセージを受信していないというメッセージが表示されることがあります。|
| チームで作業を開始するための最小限の管理作業。 | 組織内の全員が Teams を使用していない場合、特にすべてのユーザーが teams でアクティブになっていない場合は、"孤島" モードを利用して、Teams Sonly モードに移動することが難しい場合があります。 たとえば、ユーザーのサブセットが TeamsOnly モードにアップグレードされると、これらのユーザーは Teams でのみ送信されます。 島々モードでの残りの部分については、これらのメッセージは常に Teams に表示されます。 ただし、そのような人口の一部が Teams を実行していない場合は、これらのメッセージは不在として認識されます。 |
|  | Teams を使用している場合、Skype for Business Server でオンプレミスのアカウントを持っているユーザーには、相互運用またはフェデレーションのサポートはありません。  これにより、孤島ユーザーが混在している場合は混乱を招く可能性があります。 Skype for Business Online を使用している場合や、オンプレミスの Skype for Business の一部がある場合は、混乱を招く可能性があります。   |

**注:**

<sup>2</sup>これは、ユーザーが Skype for Business Server でオンプレミスになっている場合でも同様です。 ユーザーがオンプレミスまたはオンラインのどちらであるかにかかわらず、Skype for Business Online ライセンスが有効になったままにしておきます。現在のところ、Teams のすべての機能が必要であるためです。

<sup>3</sup>Skype for Business 会議から Teams の会議への移行は、個々のユーザーに TeamsUpgradePolicy を適用した場合にのみトリガーされ、テナントごとには表示されません。 詳細については、「[会議の移行](#meeting-migration)」をご覧ください。 



## <a name="managed-transition-method-using-skype-for-business-modes"></a>管理された切り替え方法 (Skype for Business モードを使用)

組織によっては、Skype for Business から Teams への移行により、エンドユーザーにより簡単で予測可能なエクスペリエンスを提供することができます。 このモデルでは、IT 管理者は、TeamsUpgradePolicy で Skype for Business モードの1つを使用して、teams Sonly モードに移行する前に、どのユーザーを Skype for Business に残しているかを明示的に指定します。 選択したユーザーを teams に移行する準備ができたら、管理者はそのユーザーのモードをチームに更新します。  展開が進むにつれて、Skype for Business から teams への移行により多くのユーザーが移行されます。  切り替え中:

- Skype for Business を使っているユーザーは、他のユーザーのチームまたは Skype for Business クライアントからの通信が発生したかどうかに関係なく、Skype for business クライアントですべての着信チャットと通話を受け取ることができます。 また、これらの Skype for Business ユーザーの場合、Teams クライアントでの通話とチャット機能は無効になり、エンドユーザーの混乱を防ぎ、適切なルーティングを確実に行うことができます。 

- チーム内のユーザーは、チーム、Skype for Business、または任意のフェデレーションユーザーの通信の種類に関係なく、すべての着信チャットと通話をチームクライアントで受信します。 

「管理された切り替え方法」では、島々の方法とは異なり、Skype for Business のユーザーとチームは互いに連絡を取ることができます。 Skype for Business ユーザーと Teams ユーザーの間の通信は、相互運用性または "相互運用" と呼ばれます。 (「[相互運用性](#interoperability)」をご覧ください。)相互運用通信は、Skype for Business のユーザーと Teams 内の別のユーザーとの間でチャットや通話を行うために、1対1の通信として使用できます。 また、招待されたユーザーはいつでも Skype for Business 会議または Teams 会議に参加できます。ただし、会議の種類に対応したクライアントを使用する必要があります。 詳細については、「[会議](#meetings)」を参照してください。

通常、管理された切り替えのユーザーは、孤島モードではないため、ユーザーのプレゼンスは、他のユーザーがどのクライアントを使用しているかに関係なく一貫しています。 ユーザーが Skype for Business モードのいずれかである場合、その他のすべてのユーザーには、Skype for Business でそのユーザーのアクティビティに基づいてプレゼンスが表示されます。 同様に、ユーザーが Teams の唯一のモードにある場合、他のすべてのユーザーには、そのユーザーのチームのアクティビティに基づいてプレゼンスが表示されます。 詳細については、「[プレゼンス](#presence)」を参照してください。

チームの使用を開始していない組織の場合、管理者は、テナント全体モードを孤島から Sfbwithteamab に変更する必要があります。 (既にチームを使用している組織の場合、この変更が適用されないようにするには、管理者が Teams で既にアクティブになっている grandfather のユーザーである必要があります。 詳細について[は、「アイランドモードで Teams を既に使用している組織の管理されたアップグレード](#a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)」を参照してください。)

モードが島々から Sfbwithteamab に変更された場合、チームを使用していないユーザーには、Skype for Business の使用方法に違いはありません。 ただし、ユーザーが Teams の使用を開始する必要がある場合は、Teams & チャネル、ファイルなどの機能に対してのみ公開されます。 チャット、通話、会議のスケジュール設定は、Teams では使用できません。管理者は、これらの機能の目的のクライアントとして Skype for Business を指定したためです。  

注: ユーザーが孤島からいずれかの Skype for Business モードに変更した場合、ユーザーが a と通信する他のユーザーのチームクライアントは、ユーザー A の適切なクライアントに通信をルーティングできるように、ユーザー a のモードが変更されたことを知る必要があります。 ユーザー A とのネイティブのチーム間チャットを既に確立しているユーザーの場合、その他のユーザーのチームクライアントが、島から任意の Skype for Business モードへのモードの変更を認識できるようになるまで、最大36時間かかることがあります。   これに対して、既存のユーザーに対する変更は、2時間以内に他のクライアントによって検出されます。

管理者は、ユーザーのモードを Teams に更新することで、特定のユーザーのチャット、通話、会議のスケジュール設定を一度に1つずつ行うことができます。  

または、最初に、SfBWithTeamsCollabAndMeetings モードを使用して Skype for Business のチャットや通話機能を残しながら、会議のスケジュールのみを Teams にシフトすることもできます。 このモードでは、組織は会議のためにチームに切り替えることができます。ユーザーがまだ TeamsOnly モードに移行する準備ができていない場合 (通常は、既存の PSTN 機能を移行するために時間がかかる場合があるため)。 この移行シナリオは、[まず会議](meetings-first.md)として参照されます。


次の表では、teams Sonly モードの移行手順として、Skype for Business モードを使用する場合の長所と短所をまとめています。


| 担当     |       面 |
| :------------------ | :---------------- |
| エンドユーザーに対して予測可能なルーティング。  Skype for Business または Teams (両方ではありませんが) で、すべての通話とチャットが管理者によって選択されています。  | 相互運用スレッドは、リッチテキスト、ファイル共有、画面共有には対応していません。  この作業は、オンデマンド会議で行うことができますが、これはシームレスではありません。  |
| 特定の機能が1つのクライアントでのみ利用可能であるため、エンドユーザーの混乱を回避します。  | 同じ機能セットについて、ユーザーは両方のクライアントを並べて試すことはできません。 これは、ユーザーが Skype for Business からチームへのシフトを主要なパラダイムシフトとして感じた場合に、特に大きな影響を受ける可能性があります。 |
| チームの段階的な導入を可能にします。  |  | |
| 管理者は、Skype for Business から Teams への移行を完全に制御することができます。 |  | | 
| チームが会議についてチームを使用できるようにします。チームは、完全に Teams のみに移行する準備がまだできていない場合でも、チームを使用できます。 |  | |
| 他のユーザーによって表示されるユーザーのプレゼンスは、どのクライアントを使っているかにかかわらず同じです。  |  | |

## <a name="summary-of-upgrade-methods"></a>アップグレード方法の概要

次の表は、アップグレード方法をまとめたものです。

| 左右 (島々モードを使用)     |      管理 (Skype for Business モードを使用) |
| :------------------ | :---------------- |
| ユーザーは、teams にアップグレードする前に、チャットを開始してから両方のクライアントを同時に実行する必要があります。また、どちらのクライアントにも通話が表示されることがあります。   | チャットと通話は、受信者のモードに基づいて1つのクライアントにのみ対応しています。 アップグレードされていないユーザーは両方のクライアントを実行できますが、機能のオーバーラップはありません (通話とチャットは Teams では利用できません)。  管理者は、ユーザーが Teams または Skype for Business で会議をスケジュールするかどうかを管理することもできます。   |
| ユーザーは、同じ機能のために Skype for Business と Teams を並べて使用できます。   | Skype for Business にも存在するのと同じ機能を提供することなく、管理者がチームの新しい機能をエンドユーザー (チームとチャネル) に導入できるようにします。   |
|Skype for Business と Teams の間の相互運用性は、両方のユーザーが孤島モードになっている間は存在しません。 一部のユーザーが teams にアップグレードされると、それらのユーザーと他のユーザーの間で相互運用機能の会話が維持されるようになります。 ただし、島々ユーザーは、Teams を使用して相互運用会話を回避することができます。 | Skype for Business と Teams ユーザーの間の通信には相互運用性が必要です。   |

## <a name="tools-for-managing-the-upgrade"></a>アップグレードを管理するためのツール

上で説明したいずれかの方法では、管理者は、ユーザーの共存モードを制御する[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)を使って、teams への切り替えを管理します。 各モードの詳細については、「[共存モード](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)」を参照してください。


管理者が Skype for Business モードを使って、管理された切り替えを実行するか、または既定の孤島構成から TeamsOnly モードにアップグレードするかにかかわらず、TeamsUpgradePolicy はプライマリツールです。  Teams の他のポリシーと同じように、TeamsUpgradePolicy はユーザーに直接割り当てることができます。また、テナント全体の既定として設定することもできます。 ユーザーに割り当てられた課題は、テナントの既定の設定よりも優先されます。  このツールは、Teams の管理コンソールと PowerShell の両方で管理できます。

管理者は、ユーザーが Skype for Business Online またはオンプレミスのどちらを使用しているかに関係なく、TeamsUpgradePolicy の任意のモードをユーザーに割り当てることができます。ただし、TeamsOnly モードは、既に Skype for Business Online に所属しているユーザーにのみ割り当てることができます。<sup>4</sup>  

Skype for Business のオンプレミスの、Skype for Business オンプレミスのツールセットのムーブグループユーザーを使用して、ホームオンプレミスの Skype for Business アカウントを使用しているユーザーは、オンライン (Skype for Business Online または Teams に直接) に[移行する必要があり](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)ます。 これらのユーザーは、1つまたは2つの手順のいずれかでのみ TeamsOnly 移動できます。

-   1手順: ムーブグループユーザーに-MoveToTeams スイッチを指定します。 これには、Skype for Business Server 2019 または Skype for Business Server 2015 と CU8 が必要です。

-   2つの手順: CsUser Move を実行した後、TeamsUpgradePolicy を使用しているユーザーに TeamsOnly モードを付与します。

他のポリシーとは異なり、Office 365 では TeamsUpgradePolicy の新しいインスタンスを作成することはできません。 既存のすべてのインスタンスがサービスに組み込まれています。  (Mode は、ポリシーインスタンスの名前ではなく、TeamsUpgradePolicy 内のプロパティです)。一部------------------------------------------- 特に、ユーザーに TeamsOnly モードを割り当てるには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスをそのユーザーに付与します。 すべてのインスタンスの一覧を表示するには、次のコマンドを実行します。

```
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

オンラインユーザーを TeamsOnly モードにアップグレードするには、"UpgradeToTeams" インスタンスを割り当てます。 

```
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

オンプレミスの Skype for Business ユーザーを TeamsOnly モードにアップグレードするには、オンプレミスのツールセットで Move-CsUser を使用します。

```
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

テナント内のすべてのユーザーのモードを変更するには、明示的なユーザーごとのアクセス許可を持つユーザー (優先されます) を除き、次のコマンドを実行します。

```
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Skype for Business アカウントを使用しているユーザーがいる場合は、オンプレミスの Skype for Business アカウントを使用しているすべてのユーザーに、他のモードを明示的に割り当てない限り、チームのテナントレベルで teams Sonly モードを割り当てないでください。

**注:**
<sup>4</sup>これは、ユーザーが skype for business Online をホームにしている場合にのみ、skype for business ユーザーとフェデレーションの相互運用機能を使用できるためです。

### <a name="using-notifications-in-skype-for-business-clients"></a>Skype for Business クライアントで通知を使う

管理者は、次の図に示すように、Skype for Business クライアントでエンドユーザーからの通知を提供して、ユーザーがすぐに Teams にアップグレードされることをユーザーに通知することができます。 たとえば、管理者がユーザーのグループを teams にアップグレードする予定の1週間前に、管理者は、ユーザーのグループに対してこれらの通知をオンにすることができます。 これらの通知は、NotifySfbUsers = true の TeamsUpgradePolicy のインスタンスを使って有効になります。  チーム以外のすべてのモードでは、NotifySfbUsers の2つの値に応じて、モードごとに実際に2つのインスタンスがあります。  チーム以外のすべてのモードでは、NotifySfbUsers の2つの値に応じて、モードごとに実際に2つのインスタンスがあります。 

![通知を示す図](media/teams-upgrade-sfb-with-notifications.png)

ユーザーが Skype for Business Online を使っている場合は、ユーザーと同じモードのポリシーインスタンスと NotifySfbUsers = true を割り当てます。 

ユーザーが Skype for Business Server をオンプレミスで使用している場合は、オンプレミスのツールセットを使用する必要があります。 skype for business server 2019 または CU8 for business Server 2015 が必要です。 オンプレミス PowerShell ウィンドウで、NotifySfbUsers = true を TeamsUpgradePolicy の新しいインスタンスを作成します。

```
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

次に、同じオンプレミス PowerShell ウィンドウを使用して、新しいポリシーを目的のユーザーに割り当てます。

```
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```


### <a name="meeting-migration"></a>会議の移行

ユーザーが TeamsOnly モードに移行されると、既定では、自分が開催した既存の Skype for Business 会議が Teams に変換されます。 必要に応じて、TeamsOnly モードをユーザーに割り当てるときに、既定の動作を無効にすることができます。 オンプレミスからユーザーを移動する場合は、オンラインユーザーアカウントで機能するように、会議をクラウドに移行する必要がありますが、-MoveToTeams を指定しない場合、会議はチームに変換されるのではなく、Skype for Business 会議として移行されます。 

テナントレベルで teams のみのモードを割り当てる場合、ユーザーに対して会議の移行はトリガーされません。 テナントレベルで teams Sonly モードを割り当て、会議を移行する場合は、PowerShell を使用してテナント内のユーザーの一覧を取得し (たとえば、必要なフィルターを持つ Csonline ユーザーを使用して)、これらの各ユーザーをループして会議を開始することができます。開始-Csexmigration 移行を使用した移行。 詳細については、「[会議移行サービス (MMS) の使用](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Skype for Business Server がオンプレミスの組織に関するその他の考慮事項

- Skype for Business ハイブリッドを設定することは、TeamsOnly モードに移行するための前提条件となります。 ハイブリッドなしでは、島々を使用することはできませんが、ハイブリッドではなく、ユーザーが Skype for Business オンプレミスから Skype for Business Online に移行されるまでは、Teams Sonly モードへの切り替えを行うことはできません ( [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)を使用)。 詳細については、「[ハイブリッド接続を構成する](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。

- オンプレミスの Skype for Business アカウントを所有している Teams ユーザー (つまり、引っ越しユーザーを使用してクラウドに移動されていない場合) は、Skype for Business ユーザーとの相互運用はできません。また、外部ユーザーとのフェデレーションを行うこともできません。 この機能は、ユーザーがクラウドに移動した場合にのみ使用できます (孤島モードの場合、またはチームのユーザーのみ)。 

- Skype for Business アカウントを使用しているユーザーがいる場合は、オンプレミスの Skype for Business アカウントを使用しているすべてのユーザーに、他のモードを明示的に割り当てない限り、チームのテナントレベルで teams Sonly モードを割り当てないでください。 

- ユーザーが正しい Skype for Business の属性を使用して、Azure AD に正しく同期されていることを確認する必要があります。 これらの属性は、"Msrtcsip-userenabled true-" というすべてのプレフィックスです。 ユーザーが Azure AD と適切に同期されていない場合、Teams の管理ツールでは、これらのユーザーを管理することはできません。 詳細については、「 [Teams および Skype For business 用に AZURE AD Connect を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)」を参照してください。

- ユーザーがオンプレミスからクラウドに移動されると、そのユーザーによって開催された会議は、Skype for Business Online または Teams に移行されます。-MoveToTeams スイッチが指定されているかどうかによって異なります。

- オンプレミスユーザーのために Skype for Business クライアントに通知を表示するには、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。 NotifySfbUsers パラメーターのみがオンプレミスユーザーに関連します。  オンプレミスユーザーは、TeamsUpgradePolicy のオンラインインスタンスからモードを受け取ります。 [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)のメモを参照してください。 

>[!NOTE]
> 2019年9月3日以降に作成されたすべての新しいテナントは、管理者がダウングレードすることなく、TeamsOnly テナントとして作成されます。 9月3日より前に Office 365 サブスクリプションを使用していなかった Skype for Business Server がオンプレミスの組織では2019、Office 365 を使ってサブスクリプションを取得すると、Microsoft サポートに連絡して、テナントのダウングレードを行う必要があります。 


## <a name="perform-the-upgrade-for-your-organization"></a>組織のアップグレードを実行する

このセクションでは、次のアップグレードオプションについて説明します。

- サイドバイサイドアップグレード (孤島モードを使用)
- チームの使用をまだ開始していない組織の管理されたアップグレード
- 組織の管理されたアップグレードであり、既に孤島モードで Teams を使用しています。

### <a name="side-by-side-upgrade-using-islands-mode"></a>サイドバイサイドアップグレード (孤島モードを使用)

サイドバイサイドアップグレードオプションの場合:

- 組織全体の迅速なアップグレードを実行できる場合は、このオプションを検討してください。  両方のクライアントを実行するときに混乱を招く可能性があるため、この期間を最小限に抑えることをお勧めします。 ユーザーが両方のクライアントを実行できることを確認する必要があります。

- このオプションは、既定のモデルであり、Office 365 ライセンスを割り当てることを除き、チームを開始するための管理者アクションは必要ありません。 ユーザーが既に Skype for Business Online を使用している場合は、既にこのモデルに登録されている可能性があります。

- サイドバイサイドモードを終了して、TeamsOnly に移動することは難しい場合があります。 アップグレードされたユーザーは Teams 経由でのみ通信するため、そのユーザーと通信する組織内の他のすべてのユーザーは、Teams を使用している必要があります。  チームの使用を開始していないユーザーがいる場合、そのユーザーは見つからないメッセージに対して公開されます。 さらに、Skype for Business のオンラインユーザーのみが表示されるわけではありません。 一部の組織では、テナントのグローバルポリシーを使用してテナント全体のアップグレードを実行します。ただし、これを避けるためには、すべてのユーザーがアップグレードの準備ができてから待つ必要があります。


### <a name="a-managed-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>チームの使用をまだ開始していない組織の管理されたアップグレード

組織が Teams でアクティブなユーザーをまだ持っていない場合は、最初の手順として、TeamsUpgradePolicy の既定のテナント全体のポリシーを、たとえば「Sfbwithteams Ab」などの Skype for Business モードのいずれかに設定します。  まだ Teams を使っていないユーザーには、動作の相違点が表示されません。 ただし、テナントレベルでこのポリシーを設定することで、ユーザーのアップグレードを開始して、アップグレードされていないユーザーとの通信を行うことができるようになります。  パイロットユーザーを特定したら、それを teams にアップグレードすることができます。  オンプレミスの場合は、Move-CsUser を使用します。 オンラインになっている場合は、TeamsUpgradePolicy を使用して、チームのメンバーのみを割り当てることができます。  既定では、これらのユーザーによってスケジュールされたすべての Skype for Business 会議は、Teams に移行されます。

主要なコマンドを次に示します。

1. テナント全体の既定のモード Sfbwithteams並べ Ab は、次のように設定します。

   ```
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 次のようにして、ユーザーを teams にアップグレードします。

   - ユーザがすでにオンラインの場合は、次の操作を行います。

     ```
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - ユーザーがオンプレミスの場合:

     ```
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

備考
 
- テナント全体のポリシーを Sfbwithteams SSfbWithTeamsCollabAndMeetings Ab に設定する代わりに、これをに設定することができます。 これにより、すべてのユーザーが Teams ですべての新しい会議をスケジュールするようになります。
- Move-CsUser はオンプレミスツールのコマンドレットです。 MoveToTeams スイッチを使用するには、CU8 で Skype for Business Server 2019 または Skype for Business Server 2015 が必要です。 以前のバージョンを使用している場合は、最初にユーザーを Skype for Business Online に移動し、そのユーザーに teams Sonly モードを付与することができます。
- 既定では、TeamsOnly モードにアップグレードした場合、または SfbWithTeamsCollabAndMeetings モードを割り当てている場合、Skype for Business 会議はチームに移行されます。  

次の図は、チームの前の使用がない組織の管理されたアップグレードの概念フェーズを示しています。 棒の高さはユーザーの数を表します。 アップグレードのフェーズ中には、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは、相互運用機能を使用するユーザーのみを対象として、またはその逆のやり取りを行うことができます。

![チームを以前に使用したことがないマネージアップグレードを示す図](media/teams-upgrade-1.png)


### <a name="a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>組織の管理されたアップグレードであり、既に孤島モードで Teams を使用しています。

組織内の一部のユーザーが、孤島モードでチームを積極的に使用している場合は、既存のユーザーから機能を削除したくないと考えられます。 そのため、テナント全体のポリシーを変更する前に、追加の手順が必要です。 この問題を解決するには、テナント全体のポリシーを Sfbwithteamsgrandfather Ab に設定する前に、これらの既存のアクティブなチームユーザーを "" にします。  この操作を完了すると、次のようにして展開に進むことができます。ただし、チームでアクティブになっていたユーザーは、島々モードになり、残りのユーザーは Sfbwithteamswithab モードになります。 これらのユーザーは、チームのユーザーに段階的に移行できます。

1. Teams でアクティブなユーザーを見つけるには、次のようにします。

   1. Office 365 管理ポータルで、左側のナビゲーションで [レポート]、[使用状況] の順に移動します。 
   2. [レポートの選択] ドロップダウンで、[Microsoft Teams]、[ユーザーアクティビティ] の順に選択します。 これにより、Teams でアクティブになっているユーザーのエクスポート可能なテーブルが表示されます。 
   3. [エクスポート] をクリックし、Excel を開き、[フィルター] をクリックして、Teams でアクティブになっているユーザーのみを表示します。

2. 手順1で検出されたアクティブな Teams ユーザーごとに、リモート PowerShell でそれらの単位を割り当てます。 これにより、次の手順に進むことができ、ユーザーエクスペリエンスを変更することはできなくなります。  

   ```
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. テナント全体のポリシーを SfbWithTeamsCollab に設定します。

   ```
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 選択したユーザーを TeamsOnly モードにアップグレードします。 ユーザーのアップグレードは、島々モードまたは Sfbwithteamsの各モードで行うことができます。ただし、ユーザーが孤島モードで実行されているときに混乱を招く可能性を最小限に抑えるためには、まず、孤島モードでユーザーをアップグレードすることをお勧めします。   

   Skype for Business Online に所属しているユーザーの場合:  

   ```
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   オンプレミスの Skype for Business Server を使用しているユーザーの場合:  

   ```
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

次の図は、アクティブな孤島ユーザーが初めて存在する、管理された遷移の概念フェーズを示しています。 バーの高さは、ユーザーの数を表します。 アップグレードのフェーズ中には、すべてのユーザーが相互に通信できます。  Skype for Business ユーザーは、相互運用機能を使用するユーザーのみを対象として、またはその逆のやり取りを行うことができます。


![アクティブなユーザーとの諸島モードでのマネージアップグレードを示す図](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>PSTN 通話に関する考慮事項

PSTN 通話機能が含まれている場合は、次の4つのシナリオが考えられます。

- *Microsoft の通話プランを使用した、Skype For Business Online のユーザー*。 アップグレードすると、このユーザーには引き続き Microsoft 通話プランが設定されます。

- Skype for business のオンプレミスまたはクラウドコネクタエディションの*オンプレミスの音声機能を使用した、skype For Business Online のユーザー* 。 チームへのユーザーのアップグレードは、ユーザーの移行によって、ユーザーが PSTN 機能しかないことを確認するために、ルーティングを直接ルーティングするように調整する必要があります。

- *エンタープライズ voip がオンプレミスの Skype For business のユーザー。オンラインに移行し、オンプレミスの PSTN 接続を維持し*ます。  このユーザーを Teams に移行するには、ユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行する必要があります。また、ユーザーの移行を使用して、その移行を直接ルーティングすることが必要になります。 

- *エンタープライズ voip がオンプレミスの Skype For business のユーザー*。オンラインに移行し、Microsoft の通話プランを使用します。  このユーザーを Teams に移行するには、ユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行する必要があります。または、そのユーザーの電話番号のポートを Microsoft の通話プランまたは B に移行する必要があります。新しい加入者番号を割り当てるには、利用可能な地域

この記事では、概要のみを説明します。  詳細については、「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)と[通話プラン](calling-plan-landing-page.md)」を参照してください。 さらに、Teams での電話システムの使用は、ユーザーが TeamsOnly モードの場合にのみサポートされることに注意してください。  ユーザーが諸島モードの場合、電話システムは Skype for Business でのみサポートされます。 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Skype for Business Online から Microsoft 通話プラン 

これは、音声が関連する最も簡単なアップグレードシナリオです。 

1. ユーザーに Teams ライセンスが割り当てられていることを確認します。 既定では、Office 365 ライセンスを割り当てている場合、Teams は有効になっているため、Teams ライセンスを無効にしていない場合は、操作は必要ありません。

2.  ユーザーが既に電話番号を使用して Microsoft 通話プランを所有している場合は、必要な変更は、TeamsUpgradePolicy でユーザーのチームのモードのみに設定することだけです。  TeamsOnly モードを割り当てる前に、着信 PSTN 通話はユーザーの Skype for Business クライアントに表示されます。 TeamsOnly モードにアップグレードした後は、着信 PSTN 通話はユーザーのチームクライアントに表示されます。  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>Skype for Business Online からオンプレミスのボイスを利用

このシナリオでは、ユーザーは既に Skype for Business Online に登録されていますが、PSTN 接続は、ハイブリッドモードまたはクラウドコネクタエディションの Skype for Business Server を使用してオンプレミスになっています。 PSTN 機能を使用して、これらのユーザーを teams Sonly モードに移行すると、PSTN trunks は、オンプレミスのセッションボーダーコントローラー (SBC) を使って、クラウド内の直接ルーティングサービスに直接接続することができます。

基本的な手順を以下に示します。  手順1-4 は提示された順序で表示されますが、任意の順序で実行できます。 重要なのは、手順5の前にこれらの手順を完了する必要があるということです。

1. テナント全体のポリシーを Skype for Business モードのいずれかに設定する場合は、既に説明したように、既存の孤島ユーザーに対して明示的に grandfather を作成してください。

2. テナントを直接ルーティング用に構成します。 詳しく[は、「直接ルーティングのテナントごとの構成」を](#summary-of-per-tenant-configuration-of-direct-routing)ご覧ください。

3. 必要に応じて、これらのユーザーに対してさまざまな Teams のポリシーを構成します (たとえば、TeamsMessagingPolicy、TeamsMeetingPolicy など)。 この操作はいつでも行うことができますが、アップグレード時にユーザーが正しい構成を使用できるようにするには、ユーザーが TeamsOnly モードにアップグレードされる前に、この操作を行うことをお勧めします。

4. 音声移行のための選択ユーザーを準備します。 
   - 必要に応じて、Teams ライセンスを割り当てます。  ユーザーが既に Skype for Business Online オンプレミスボイスで機能している場合、ユーザーは既に Skype for Business プラン2と Microsoft 電話システムを使用しています。 Skype for Business Online Plan 2 ライセンスも含めて、両方のプランを有効のままにしておきます。  
   - 目的の OnlineVoiceRoutingPolicy を割り当てます。 

5. ユーザーをアップグレードする: これらの手順は調整する必要があります。 

   - Office 365 で、ユーザーを TeamsOnly モード (Grant-CsTeamsUpgradePolicy) にアップグレードします。
   - SBC では、オンプレミスの仲介サーバーではなく直接ルーティングに通話を送信することで、着信を有効にするために音声ルーティングを構成します。


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Skype for Business Server のオンプレミスの企業 Voip から直接ルーティング

このシナリオでは、ユーザーはまだオンプレミスの Skype for Business を使用しており、PSTN 接続もオンプレミスになっています。 PSTN 機能を使用して、これらのユーザーを teams Sonly モードに移行することで、これらのユーザーを直接ルーティングし、ユーザーをクラウドに移行することができます。 
 
基本的な手順を以下に示します。  手順1-5 は提示された順序で表示されますが、任意の順序で実行できます。 重要なのは、手順6の前にこれらの手順を完了する必要があるということです。

1. テナント全体のポリシーを Skype for Business モードのいずれかに設定する場合は、既に説明したように、既存の孤島ユーザーに対して、grandfather を明示的に指定してください。

2. まだインストールしていない場合は、[組織を Skype For business ハイブリッド用に構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。

3. テナントを直接ルーティング用に構成します。 詳しく[は、「直接ルーティングのテナントごとの構成」を](#summary-of-per-tenant-configuration-of-direct-routing)ご覧ください。

4. 必要に応じて、これらのユーザーに対してさまざまな Teams のポリシーを構成します (たとえば、TeamsMessagingPolicy、TeamsMeetingPolicy など)。 この操作はいつでも行うことができますが、アップグレード時にユーザーが正しい構成を確実に使用できるようにするには、ユーザーが teams にアップグレードされる前に行うことをお勧めします。

5. 必要に応じて、Office 365 ライセンスを割り当てます。  ユーザーには、Teams と Skype for Business Online Plan 2、および電話システムの両方が必要です。 Skype for Business Online プラン2が無効になっている場合は、もう一度有効にします。  

6. ユーザーをアップグレードする: これらの手順は調整する必要があります。 

   - オンプレミスの Skype for Business のツールを使用して、[チームの切り替え] を使用して CsUser を実行します。 -MoveToTeams でサポートされていないバージョンの Skype for Business Server を使用している場合は、最初に Move-CsUser を実行してから、テナントのリモート PowerShell または Teams の管理コンソールで、TeamsOnly モードを割り当てる必要があります。

   - SBC では、オンプレミスの仲介サーバーではなく直接ルーティングに通話を送信することで、着信を有効にするために音声ルーティングを構成します。 

   - Office 365 での通話の発信を有効にするには、関連する OnlineVoiceRoutingPolicy を割り当てます。 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>オンプレミスの Skype for Business Server (エンタープライズ Voip、Microsoft 通話プラン)

このシナリオでは、ユーザーはまだオンプレミスの Skype for Business を使用しており、PSTN 接続もオンプレミスになっています。 PSTN 機能を使用して、これらのユーザーを teams Sonly モードに移行するには、ユーザーをクラウドに移行して、古い通信事業者から Microsoft の通話プランに番号を移行するか、ユーザーに新しい番号を割り当てることができます。 

基本的な手順を以下に示します。手順1-5 は提示された順序で表示されますが、任意の順序で実行できます。 重要なのは、手順6の前にこれらの手順を完了する必要があるということです。 

1. テナント全体のポリシーを Skype for Business モードのいずれかに設定する場合は、既に説明したように、既存の孤島ユーザーに対して、grandfather を明示的に指定してください。 

2. まだインストールしていない場合は、[組織を Skype For business ハイブリッド用に構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。 

3. 必要に応じて、これらのユーザーに対してさまざまな Teams のポリシーを構成します (たとえば、TeamsMessagingPolicy、TeamsMeetingPolicy など)。 この操作はいつでも行うことができますが、アップグレード時にユーザーが正しい構成を確実に使用できるようにするには、ユーザーが teams にアップグレードされる前に行うことをお勧めします。 

4. 必要に応じて、Office 365 ライセンスを割り当てます。ユーザーには、Teams と Skype for Business Online Plan 2、および電話システムの両方が必要です。 Skype for Business Online プラン2が無効になっている場合は、もう一度有効にします。  

5. ユーザー用の電話番号を取得します。 (詳細については[、「組織の電話番号を管理](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)する」を参照してください。)

   - 電話番号を再利用する場合は、お使いの携帯電話会社に移植要求を送信してください。  
   - または、Microsoft から直接新しい番号を取得することもできます。 

6. ユーザーをアップグレードします。 オンプレミスの Skype for Business のツールを使用して、[チームの切り替え] を使用して CsUser を実行します。  

    - Microsoft に番号を移行する場合は、ポートが発生したときにこの操作が実行されるタイミングを調整する必要があります。 

    - Microsoft の新しい番号を使用している場合は、ユーザーの LineUri を変更する必要があります。これはオンプレミスのツールで実行し、Azure AD Connect 経由でクラウドに同期する必要があります。 Azure AD Connect が変更を同期するときには、ユーザーの移動操作が同時に実行されるようにする必要があります。 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接ルーティングのテナントごとの構成の概要 

1. [この一覧](direct-routing-border-controllers.md)を確認して、セッション境界コントローラー (SBC) が直接ルーティングでサポートされていることを確認します。 適切なバージョンのファームウェアがインストールされていることも確認する必要があります。  

2. オンプレミスの SBC を Teams のダイレクトルーティングサービスとペアリングします。 詳細については、「 [SBC と電話システムのダイレクトルーティングサービスを組み合わせる](direct-routing-configure.md#pair-the-sbc-to-the-direct-routing-service-of-phone-system)」を参照してください。 

3. この構成は、基本的にオンプレミス構成のミラーです。 オンライン構成は次の要素で構成されます。 
   - OnlineVoiceRoutingPolicy (オンプレミスの VoiceRoutingPolicy に基づいて、ユーザーを Skype for Business Online から移行する場合は VoicePolicy、エンタープライズ Voip でオンプレミスからユーザーを移行する場合はに基づいてください。
   - OnlinePSTNUsage オブジェクト (オンプレミス PSTN の使用状況に基づく)。 
   - OnlineVoiceRoute オブジェクト (オンプレミス VoiceRoute に基づく)。 

詳細については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>移行中に EnterpriseVoiceEnabled プロパティを管理する 

直接ルーティングと Microsoft 通話プランのどちらを使う場合も、ユーザーは PSTN 機能を使用するために、Azure AD で EnterpriseVoiceEnabled = true を持っている必要があります。  EnterpriseVoiceEnabled ("EV-enabled") は、オンプレミスのディレクトリとクラウドの両方に存在するプロパティ (ポリシーではありません) です。 クラウドの価値は、Teams で重要です。  EV 対応の取得方法についての正確なロジックは、次のシナリオによって異なります。 

- ユーザーがオンプレミスの Skype for Business Server で EV に対応しており、ユーザーをクラウドに移行する前に、ユーザーに電話システムのライセンスが割り当てられている場合、オンラインユーザーには EV-対応 = true が提供されます。 

- 既存の TeamsOnly または Skype for Business Online ユーザーに電話システムライセンスが割り当てられている場合、EV 対応は既定では true に設定されません。  これは、電話システムのライセンスを割り当てる前にオンプレミスのユーザーがクラウドに移動された場合にも当てはまります。 どちらの場合も、管理者は次のコマンドレットを指定する必要があります。 

  ```
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>チームと Skype for Business の共存

このセクションでは、どのモードやどのアップグレード方法を使用しているかに関係なく、同じ組織内で Teams と Skype for Business クライアントの両方を実行しているときに発生する可能性のある動作についてまとめます。

- [会議](#meetings)
- [運用性](#interoperability)
- [チームの会話-相互運用とネイティブスレッドの比較](#teams-conversations---interop-versus-native-threads)
- [プレゼンス](#presence)
- [フェデレーション](#federation)
- [連絡先](#contacts)

### <a name="meetings"></a>会議

ユーザーは、どのような種類の会議に参加していても、Skype for Business とチームのどちらであっても、いつでも参加することができます。  ただし、ユーザーは会議の種類に一致する対応クライアントと会議に参加する必要があります。

- 会議が Teams 会議の場合、すべての参加者 (チームの参加者のみ、または Skype for Business のユーザー) は、Teams クライアントを使って会議に参加します。 Teams がインストールされていない場合は、会議に参加しようとしたときに、ユーザーは web に転送されます。

- 会議が Skype for Business 会議の場合、すべての参加者 (チームのメンバーまたは Skype for Business のユーザーのいずれかに関係なく) は、Skype for Business クライアントを使って会議に参加します。 Skype for Business クライアントがインストールされていない場合、ユーザーは web に転送され、Skype 会議アプリを使用して参加することになります。

会議を開催する場合、スケジュールされた会議の種類は、次の表に示すように、開催者のモードに基づいています。

| 開催者のモード    |      動作 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings |    Teams でスケジュールされているすべての会議。 Skype for Business アドインは Outlook では使用できません。 | 
| Sfbwithteamsteams Ab、Sfbのみ   | Skype for Business でスケジュールされているすべての会議。 Teams アドインは Outlook では使用できません。 | 
| アイランド |     会議は、Skype for Business または Teams のいずれかでスケジュールできます。 どちらのアドインも Outlook で利用できます。 | 


### <a name="interoperability"></a>運用性

一部のシナリオでは、チームは Skype for Business との相互運用性 (相互運用機能) をサポートしています。 相互運用通信とは、Skype for Business ユーザーと Teams ユーザー間のチャットや通話を指します。  相互運用通信は、2人のユーザー間でのみ行うことができます。複数の相手とのチャットや通話の発信や、ユーザーの追加はサポートされていません。

2人のユーザ間の相互運用チャットまたは通話は、次のいずれかの条件に該当する場合に作成されます。

- 1人のユーザーが Teams を使用していて、他のユーザーが Skype for Business を使用している。

- 最初の通信の受信者のモードは、同じ組織内にいるユーザーがいる場合は、島々 (それ以外の場合は、通信が同じクライアントに着陸する) ではありません。 フェデレーションシナリオでは、送信ユーザーは Teams を使用していますが、受信者は TeamsOnly モードではありません。 

- チームユーザーは、オンプレミスの Skype for Business アカウントも持っていません。 

相互運用通信では、チャットはテキスト形式のみです。 また、*相互運用性チャットで*は、ファイル共有とスクリーン共有はできません。 ただし、相互運用スレッド内のユーザーは、次に示すように、相互運用チャット内からオンデマンド会議を作成することによって、ファイルや画面の共有を簡単に実現できます。

- チームユーザーが画面を共有しようとすると、オンデマンドのチーム会議が自動的に作成され、その会議への招待リンクが Skype for Business ユーザーのクライアントに送信されます。 リンクをクリックすると、Skype for Business ユーザーは [チーム] を開き、会議に参加します。 両方のユーザーが Teams 会議に参加し、必要に応じて共有できるようになりました。

- Skype for Business ユーザーが2018以降のクライアントを使用していて、コンテンツを共有しようとすると、オンデマンドの Skype for Business 会議が自動的に作成され、その会議への招待リンクがチームユーザーのクライアントに送信されます。 リンクをクリックすると、Teams ユーザーは Skype for Business 会議に参加しようとします。 Teams ユーザーが Skype for Business クライアントをインストールしている場合は、サインインするように求めるメッセージが表示されます (まだサインインしていない場合)。  Teams ユーザーが Skype for Business クライアントをインストールしていない場合は、web バージョンを使用するように求められます。 両方のユーザーがサインインすると、Skype for Business 会議に参加し、必要に応じて共有できます。

### <a name="teams-conversations---interop-versus-native-threads"></a>チームの会話-相互運用とネイティブスレッドの比較

相互運用通信では、ネイティブチームの会話のすべての機能がサポートされていないため、teams クライアントはチーム間の会話スレッドとチーム同士のコミュニケーションを別々に管理します。 ユーザーインターフェイスでは、これらの会話の表示方法が異なります。相互運用スレッドは、次のようにして、通常のネイティブな Teams スレッドと区別できます。

- リッチテキスト、ファイル/スクリーン共有、ユーザーの追加ができないコントロールのコントロールがない。
- ターゲットユーザーのアイコンに対する変更。 Skype for Business の "S" が表示されています。

これらの違いを次のスクリーンショットに示します。

ユーザー G3 テストによるネイティブチーム対チームの会話

![ネイティブのチーム対チームの会話を示す図](media/teams-upgrade-native-thread.png)

同じユーザー G3 テストでの相互運用会話

![相互運用チームとチーム間の会話を示す図](media/teams-upgrade-interop-thread.png)

スレッドが作成されると、その型は変更されません。 作成したチームの相互運用スレッドは、常にターゲットユーザーの Skype for Business クライアントにルーティングします。 ネイティブスレッドは、常にターゲットユーザーのチームクライアントにルーティングします。  受信者のユーザーモードが変更された場合、そのユーザーに対する既存のチームスレッドは機能しなくなり、次のスクリーンショットに示すように、新しいネイティブ会話を開始するためのリンクと共にそのチャットにメモが表示されます。 詳細については、「[既存のスレッドからのチャットと通話](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads)」を参照してください。


![Skype for Business ユーザーがアップグレードされたチャットを示す図](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>プレゼンス

特定のユーザーのプレゼンスは、クライアントを介したサービスでのユーザーのアクティビティに基づきます。 このプレゼンスが公開され、他のユーザーに表示されます。  Skype for Business と Teams は別々のクライアントと別々のサービスであるため、各サービスにはユーザー向けの独自のプレゼンス状態があります。   また、Teams のプレゼンスサービスと Skype for Business Online の間で同期されています。  これにより、1つのサービスが、必要に応じて、他のサービスからユーザーのプレゼンスを公開する可能性があります。 

プレゼンスの公開動作は、ユーザーのモードに基づいています。 基本的なケースは3つあります。

- ユーザーが TeamsOnly モードにある場合は、どのクライアントを使うかに関係なく、他のすべてのユーザーにそのユーザーの Teams のプレゼンスが表示されます。

- ユーザーが Skype for Business モードのいずれかにいる場合は、どのクライアントを使っているかに関係なく、他のすべてのユーザーにそのユーザーの Skype for Business のプレゼンスが表示されます。

- ユーザーが諸島モードの場合、Skype for Business と Teams で公開されたプレゼンスは独立しているため、同じ組織内のユーザーに表示されるプレゼンスは、他のユーザーのクライアントによって異なります。 フェデレーションされた組織内のユーザーには、そのユーザーの Skype for business のアクティビティに基づいてそのユーザーのプレゼンスが表示されます。フェデレーションされたトラフィックは、Skype for Business の部門間モードのユーザーによるものであるためです。

たとえば、ユーザー A は諸島モードであるとします。 ユーザー A が Teams でアクティブになっているが、Skype for business にサインインしていない場合、他のユーザーにはチームクライアントからのユーザー A がアクティブとして表示されますが、Skype for Business クライアントではユーザー a がオフラインとして表示されます。 これは、ユーザーがクライアントを実行していない場合にはアクセスできないため、設計によるものです。 

詳細については、「[プレゼンス](coexistence-chat-calls-presence.md#presence)」を参照してください。

### <a name="federation"></a>フェデレーション

Skype for Business を使用して Teams から別のユーザーにフェデレーションを行うには、Teams ユーザーが Skype for Business でオンラインになっている必要があります。 TeamsUpgradePolicy は、フェデレーションされた受信チャットと通話のルーティングを制御します。 フェデレーションされたルーティングの動作は、同じテナントの場合のシナリオと同じものです (アイランド モードの場合を除く)。 受信者がアイランド モードの場合の動作は、次のようになります。

- 受信者がフェデレーションされたテナントにある場合、Skype for Business のチームの土地から開始されたチャットと通話。
- Teams から開始されたチャットと通話は、受信者が同じテナントにいる場合、Teams に届きます。
- Skype for business から開始されたチャットと通話は、常に Skype for Business に着陸します。

Teams ユーザーと Skype for Business の間のフェデレーションチャットは相互運用スレッドであるため、リッチテキストと共有はできません。 フェデレーションされたチャットは、同じような方法で同じテナントの相互運用スレッドに公開されます。ただし、ユーザーが外部であることを示すメモはありません。

Teams で初めてフェデレーションが導入された場合、2つの Teams ユーザー間のフェデレーションチャットは相互運用スレッドでもありましたが、今後は、ネイティブチームフェデレーションが導入され、これによって teams のみのモードにいるユーザー間の会話についてのすべての機能が提供されます。 . 

詳しくは、「[新しいチャットまたは通話のフェデレーションルーティング](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls)」をご覧ください。

### <a name="contacts"></a>連絡先

Teams と Skype for Business には、連絡先のリストが個別に用意されています。 これは、あるシステムで行われた連絡先の追加、削除、変更が、他のシステムに同期されていないことを意味します。 ただし、次の2つのイベントのいずれかが発生すると、Skype for Business の連絡先が自動的にチームにコピーされます。 

- Skype for Business Online ユーザーの場合は、チームに初めてログインしたときに、Skype for Business の連絡先が Teams にコピーされます。  この動作は、Skype for Business Server のオンプレミスアカウントを使用しているユーザーは使用できません。  

- ユーザーが teams にアップグレードされた (TeamsUpgradePolicy を割り当てるか、またはを使用して移動する) と、次回ユーザーが Teams にログインしたときに、Skype for Business の既存の連絡先は、既に Teams に存在する連絡先と統合されます。 この動作は、ユーザーの Skype for Business アカウントがオンプレミスかオンラインかにかかわらず発生します。 

どちらの場合も、Skype for Business から Teams への連絡先の転送は非同期であるため、Teams に連絡先が表示されるまでに数分かかることがあります。 上記の2つのイベントは、コピーをトリガーするものです。  

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Office 365 の間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[ユーザーのオンプレミスとクラウド間の移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

