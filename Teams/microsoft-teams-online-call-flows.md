---
title: Microsoft Teams 通話のフロー
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: さまざまなトポロジで Teams が Office 365 フローを使用する方法について説明します。
ms.openlocfilehash: 409af0b815c87e6d8285c3cb9a1bd8a5d61fa98b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832827"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams 通話のフロー

> [!TIP]
> このセッションでは、チームがネットワークを活用する方法と、最適なネットワーク接続を計画する方法について説明します。 [Teams ネットワーク計画](https://aka.ms/teams-networking)。

## <a name="overview"></a>概要

この記事では、さまざまなトポロジで Teams が Office 365 のコールフローを使用する方法について説明します。 また、ピアツーピアメディア通信に使用される固有のチームフローについても説明します。 このドキュメントでは、ネットワーク上でこれらのフロー、目的、およびその発生元と終了が説明されています。 この記事の目的に応じて、次のことを前提とします。

- Flow X は、オンプレミスの Office 365 クライアントによって、クラウドの Office 365 サービスと通信するために使用されます。 これは、顧客ネットワークから発信され、Office 365 のエンドポイントとして終了します。

- Flow Y は、オンプレミスの Office 365 クライアントによって、Office 365 が依存しているインターネット上のサービスと通信するために使用されます。 これは、顧客ネットワークから発信され、インターネット上のエンドポイントとして終了します。

この記事では、次の情報について説明します。

- **背景**。 Office 365 フローのスキャン、トラフィックの種類、顧客ネットワークから Office 365 サービスエンドポイントへの接続ガイダンス、サードパーティ製コンポーネントとの相互運用性、使用される原則などの背景情報を提供します。[チーム] でメディアフローを選択します。

- **さまざまなトポロジでのコールフロー**。 さまざまなトポロジでのコールフローの使い方を示します。 各トポロジについて、サポートされているすべてのフローを列挙し、これらのフローがさまざまなユースケースでどのように使用されるかを示します。 各ユースケースについて、フロー図を使ってフローの順序および選択を記述します。

- **エクスプレスルートの最適化を行っているチーム**。 簡易ルートを使用して最適化を展開するときに、これらのフローがどのように使用されるかを説明します。シンプルなトポロジで示されています。

## <a name="background"></a>背景

### <a name="network-segments"></a>ネットワークセグメント

**顧客ネットワーク**。 これは、管理および管理するネットワークセグメントです。 これには、お客さまのお客さまのお客様への接続 (有線またはワイヤレス、オフィスビル間の接続、オンプレミスのデータセンターへの接続、インターネットプロバイダへの接続、その他のプライベートピアリングなど) が含まれます。

通常、顧客ネットワークには、ファイアウォールやプロキシサーバーを備えたネットワーク境界がいくつかあります。これにより、組織のセキュリティポリシーが適用されます。また、設定して構成した特定のネットワークトラフィックのみを許可します。 このネットワークを管理するため、ネットワークのパフォーマンスを直接制御できます。また、ネットワーク上のサイトと365ネットワークの両方でパフォーマンスを検証するために、ネットワークの評価を実行することをお勧めします。

**インターネット**。 これは、顧客ネットワークの外部から Office 365 に接続しているユーザーが使用する、全体的なネットワークの一部であるネットワークセグメントです。 また、顧客ネットワークから Office 365 への一部のトラフィックでも使用されます。

**アクセスした、またはゲストプライベートネットワーク**。 これは、顧客ネットワークの外部のネットワークセグメントであり、公共のインターネットでは使用できません。たとえば、ユーザーとそのゲストがアクセスする可能性があります (たとえば、家庭用のプライベートネットワークや企業のプライベートネットワークなど、チームを展開しない場合は、ユーザーとそのユーザーを対象としています)。Teams サービスとやり取りする場合もあります)。

> [!NOTE]
> Office 365 への接続は、これらのネットワークにも適用されます。

**Office 365** これは、Office 365 サービスをサポートするネットワークセグメントです。 これは、世界各地のお客様のネットワークに近接したエッジを使用して世界中に配布されています。 機能には、トランスポートリレー、会議サーバー、メディアプロセッサが含まれます。

**簡易ルート (省略可能)**。 これは、Office 365 ネットワークへの専用接続を提供する、全体的なネットワークの一部であるネットワークセグメントです。

### <a name="types-of-traffic"></a>トラフィックのタイプ

**リアルタイムメディア**。 オーディオ、ビデオ、画面共有のワークロードをサポートする、リアルタイムトランスポートプロトコル (RTP) 内にカプセル化されたデータ。 通常、メディアトラフィックは非常に待機時間が高いため、このトラフィックは可能な限り多くのパスを使用し、トランスポート層プロトコルとして UDP または TCP を使うことをお勧めします。これは、品質の観点から対話的なリアルタイムメディアを作成するための最適なトランスポートです。. (最後の手段として、メディアは TCP/IP を使用でき、HTTP プロトコルでもトンネリングできることに注意してください。品質への影響が悪いため、お勧めしません)。RTP フローは SRTP を使って保護され、ペイロードのみが暗号化されます。

**シグナリング**。 クライアントとサーバーの間の通信リンク、またはアクティビティ (通話の開始時など) を制御するために使用される他のクライアント。 ほとんどのシグナルトラフィックでは、HTTPS ベースの REST インターフェイスが使用されますが、シナリオによっては (たとえば、Office 365 とセッション境界コントローラー間の接続)、SIP プロトコルを使います。 このトラフィックは待ち時間に非常に敏感であることを理解しておく必要がありますが、エンドポイント間の待機時間が数秒を超えると、サービスが停止したり、タイムアウトしたりする可能性があります。

### <a name="connectivity-to-office-365"></a>Office 365 への接続

チーム[にはインターネットへの接続](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)が必要。 Teams のエンドポイント Url と IP アドレス範囲は、 [Office 365 url と ip アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)に記載されています。 (TCP ポート80と443、および UDP ポート3478から3481への接続を開く必要があることに注意してください)。さらに、Teams は Skype for Business Online に依存しているため、インターネットにも接続する必要があります。

Teams メディアフロー接続は、標準の IETF 対話型接続確立 (ICE) 手順を使用して実装されます。

### <a name="interoperability-restrictions"></a>相互運用性の制限

**サードパーティメディアリレー**。 Teams メディアフロー (つまり、いずれかのメディアエンドポイントが Teams である場合) は、Teams または Skype for Business のネイティブメディアリレーのみをスキャンすることができます。 サードパーティのメディアリレーとの相互運用性はサポートされていません。 (PSTN でのサードパーティの SBC は、RTP/RTCP ストリームを終了し、SRTP を使ってセキュリティで保護されているため、次のホップには中継しないことに注意してください)。

**サードパーティ SIP プロキシサーバー**。 サードパーティの SBC/ゲートウェイでシグナリングされたチームまたは Skype for Business のネイティブ SIP プロキシをスキャンするチーム。 サードパーティの SIP プロキシとの相互運用性はサポートされていません。

**サードパーティの B2BUA (または SBC)**。 PSTN との間の Teams メディアフローは、サードパーティの SBC によって終了します。 ただし、Teams ネットワーク内のサードパーティの SBC との相互運用性 (サードパーティの SBC は2つのチームまたは Skype for Business のエンドポイントを使用している場合) はサポートされません。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Microsoft Teams で推奨されないテクノロジ

**VPN ネットワーク**。 メディアトラフィック (またはフロー 2) にはお勧めできません。 VPN クライアントでは、vpn[トンネルをバイパスするように Lync メディアを有効にする](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)ことで指定されているように、境界 vpn を使って、外部の vpn 以外のすべてのユーザーと同様にメディアトラフィックをルーティングする必要があります。

> [!NOTE]
> このタイトルは Lync を示していますが、チームにも適用されます。

**パケット図形**。 どのような種類のパケット snippers、パケット検査、またはパケット shaper デバイスは推奨されないため、品質が大幅に低下する可能性があります。

### <a name="principles"></a>指針

Microsoft Teams のコールフローを理解するのに役立つ4つの一般的な原則があります。

- Microsoft Teams の会議は、最初の参加者が参加したのと同じ地域で Office 365 によってホストされています。 (一部のトポロジではこの規則に例外がある場合は、このドキュメントで説明されていて、適切なコールフローで示されることに注意してください)。

- Office 365 の Teams メディアエンドポイントは、通話の種類に基づくメディア処理のニーズに基づいて使用されます。 (たとえば、ポイントツーポイントの通話では、クラウドのメディアエンドポイントを使用して、議事録や記録のためにメディアの処理を行うことができます。参加者が2人の会議では、クラウドのメディアエンドポイントを使用することはできません)。ただし、ほとんどの会議では、会議がホストされている場所に割り当てられる、ミキシングとルーティングの目的でメディアエンドポイントが使用されます。 顧客のネットワークファイアウォールの制限により、クライアントからメディアエンドポイントに送信されたメディアトラフィックが直接ルーティングされる場合や、必要に応じて、Office 365 でトランスポートリレーを使用する場合があります。

- ピアツーピア通話用のメディアトラフィックは、通話がクラウドでメディアエンドポイントを必要としないことを前提として、利用可能な最も直接的なルートを受け取ります (前の原則を参照)。 優先ルートはリモートピア (クライアント) に直接送信されますが、そのルートが利用できない場合は、1つ以上のトランスポートリレーがトラフィックを中継します。 メディアトラフィックは、メディアの品質に影響を与えるため、パケットコントローラー、VPN サーバーなどの横にあるサーバーではないことをお勧めします。

- シグナリングトラフィックは、常に最も近いサーバーに移動します。

選択されているメディアパスの詳細については、「 [Microsoft Teams でのメディアフローの概要-BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo)」を参照してください。

## <a name="call-flows-in-various-topologies"></a>さまざまなトポロジでのコールフロー

### <a name="teams-topology"></a>Teams のトポロジ

このトポロジは、Skype for Business Server や電話システムの直接ルーティングなど、オンプレミスの展開がなくてもクラウドから Teams サービスを利用する顧客によって使用されます。 さらに、Office 365 へのインターフェイスは、Azure Express Route を使わずにインターネット経由で行われます。

[![Microsoft Teams Online の通話フロー図01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*図 1-Teams のトポロジ*

次の点に注意してください。

- 上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。 メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。
- Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。

詳細については、次の記事の後のオプションのトポロジを参照してください。

- Skype for Business のオンプレミスの展開については、「 **Teams ハイブリッドトポロジ**」を参照してください。
- 電話システムの直接ルーティング (PSTN 接続用) については、「**ダイレクトルーティングトポロジを使用した Teams**」を参照してください。
- エクスプレスルートについては、「 **Express route の最適化」を**参照してください。

**フローの説明**:

- **フロー 2** –ユーザーのチームエクスペリエンスの一部として、顧客ネットワーク上のユーザーによって開始されたフローを表します。 これらのフローの例としては、DNS とピアツーピアメディアがあります。
- **フロー 2 '** –リモートのモバイルチームユーザーによって開始されたフロー (顧客ネットワークへの VPN を含む) を表します。
- **フロー 3** –リモートのモバイルチームユーザーによって開始されたフロー (Office 365 またはチームのエンドポイント) を表します。
- **フロー 4** –顧客ネットワーク上のユーザーによって開始されたフロー (Office 365 またはチームのエンドポイント) を表します。
- **フロー 5** – teams ユーザーと別のチームまたは顧客ネットワーク内の Skype for business ユーザーとの間のピアツーピアメディアフローを表します。
- **フロー 6** –リモートのモバイルチームユーザーと別のリモートモバイルチーム、またはインターネット上の Skype for business ユーザーとの間のピアツーピアメディアフローを表します。

#### <a name="use-case-one-to-one"></a>ユースケース: 1 対1

1対1の通話では、発信者が IP アドレス/ポート (中継によって表示されるクライアントのパブリック IP アドレスなど) で構成される一連の候補を取得する共通モデルを使います。 発信者は、これらの候補を、通話先に送信します。また、同様の候補を取得し、呼び出し元に送信します。 STUN connectivity のチェックメッセージは、どの発信者/通話相手側メディアパスが機能し、最適な作業パスが選択されているかを確認するために使用されます。 メディア (SRTP を使ってセキュリティ保護された RTP/RTCP パケット) は、選択した候補ペアを使って送信されます。 トランスポートリレーは、Office 365 の一部として展開されます。

ローカル IP アドレス/ポート候補または再帰的候補が接続されている場合、クライアント間 (または NAT を使用) 間の直接パスがメディア用に選択されます。 クライアントが顧客ネットワーク上にある場合は、ダイレクトパスを選択する必要があります。 これには、お客様のネットワーク内で直接の UDP 接続が必要です。 クライアントが両方とも nomadic クラウドユーザーである場合は、NAT/ファイアウォールによっては、メディアに直接接続が使用されている可能性があります。

1つのクライアントが顧客ネットワーク上にあり、一方が外部 (たとえば、モバイルクラウドユーザー) のクライアントである場合は、ローカルまたは再帰の候補の間の直接接続が機能していることはほとんどありません。 この場合、いずれかのクライアントからトランスポートリレー候補のいずれかを使用することをお勧めします (たとえば、内部クライアントは、Office 365 のトランスポートリレーからリレー候補を取得している必要があります)。外部クライアントは、転送された、RTP/RTCP パケットをトランスポートリレーに送信できます。 別の方法として、内部クライアントが、モバイルクラウドクライアントによって取得された relay 候補に送信されます。 メディアの UDP 接続は強くお勧めしますが、TCP はサポートされています。

**高レベルの手順**:

1. Teams ユーザーは、フロー2を使って URL ドメイン名 (DNS) を解決します。
1. Teams ユーザー A は、flow 4 を使って、Teams トランスポートリレーにメディアリレーポートを割り当てます。
1. Teams ユーザー A は、フロー 4 365 を使用して、ICE 候補を使って "招待" を送信します。
1. Office 365 は、flow 4 を使ってチームユーザー B に通知を送信します。
1. Teams ユーザー B は、flow 4 を使って Teams トランスポートリレーにメディアリレーポートを割り当てます。
1. Teams ユーザー B はフロー4を使用して、ICE 候補を使って "answer" を送信します。フロー4を使って Teams ユーザー A に戻されます。
1. Teams ユーザー A と Teams ユーザー B が ICE 接続テストを呼び出し、最適なメディアパスが選択されています (さまざまなユースケースについては、以下の図を参照してください)。
1. Teams ユーザーは、フロー4を使ってテレメトリを Office 365 に送信します。

**顧客ネットワーク内:**

[![Microsoft Teams Online の通話フロー図02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*図 2-顧客ネットワーク内*

手順7では、ピアツーピアメディアフロー5が選択されています。

メディアは双方向です。 フロー5の方向は、このドキュメント内のすべてのフローと一貫性のある接続の観点から、1つのサイドが通信を開始することを示します。 この場合、どちらのエンドポイントも顧客のネットワーク内にあるため、どの方向を使用するかは関係ありません。

**外部ユーザーに対する顧客ネットワーク (メディアトランスポートリレーによって中継されるメディア):**

[![Microsoft Teams Online の通話フロー図03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*図 3-外部ユーザーへの顧客ネットワーク (Teams トランスポートリレーによるメディアの中継)*

手順7では、[顧客ネットワーク] から [Office 365] のフロー3、[リモートモバイルチームユーザーから Office 365 へのフロー 3] が選択されています。 これらのフローは、Office 365 内の Teams トランスポートリレーによって中継されます。

[メディア] は、双方向で接続の観点から通信を開始する側を示します。 この場合、さまざまなトランスポートプロトコルとアドレスを使用して、シグナルおよびメディアにこれらのフローが使用されます。

**外部ユーザー (ダイレクトメディア) に対する顧客ネットワーク:**

[![Microsoft Teams Online の通話フロー図04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*図 4-外部ユーザー (ダイレクトメディア) に対する顧客ネットワーク*

手順7では、[顧客ネットワークからインターネット (クライアントのピア) へのフロー 2] が選択されています。

- リモートモバイルユーザーのダイレクトメディア (Office 365 経由では中継されません) はオプションです。 つまり、お客様は、このパスをブロックして、Office 365 でトランスポートリレー経由でメディアパスを強制することができます。

- メディアは双方向です。 フロー2からリモートモバイルユーザーまでの方向は、一方のサイドが接続の観点から通信を開始することを示します。

**内部ユーザーに対する VPN ユーザー (Teams トランスポートリレーによって中継されるメディア)**

[![Microsoft Teams Online の通話フロー図05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*図 5-内部ユーザーに対する VPN ユーザー (Teams トランスポートリレーによって中継されるメディア)*

VPN と顧客ネットワーク間のシグナリングはフロー 2 ' を使用しています。 顧客ネットワークと Office 365 間のシグナリングはフロー4を使用しています。 ただし、メディアは VPN をバイパスし、Office 365 の Teams メディアリレーを通じて、フロー3と4を使ってルーティングされます。

**内部ユーザー (ダイレクトメディア) に対する VPN ユーザー**

[![Microsoft Teams Online の通話フロー図06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*図 6-VPN ユーザーと内部ユーザー (ダイレクトメディア)*

VPN と顧客ネットワーク間のシグナリングはフロー 2 ' を使用しています。 顧客ネットワークと Office 365 間のシグナリングはフロー4を使用しています。 ただし、メディアは VPN をバイパスし、ユーザーのネットワークからインターネットへのフロー2を使ってルーティングされます。

メディアは双方向です。 リモートモバイルユーザーのフロー2の方向は、一方のサイドが接続の観点から通信を開始することを示します。

**外部ユーザー (ダイレクトメディア) に対する VPN ユーザー**

[![Microsoft Teams の通話フロー図07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*図 7-VPN ユーザーから外部ユーザーへの接続 (ダイレクトメディア)*

VPN ユーザーと顧客ネットワークとの間のシグナリングはフロー2を使用しており、フロー4を Office 365 に使用しています。 ただし、メディアは VPN をバイパスし、フロー6を使ってルーティングされます。

メディアは双方向です。 リモートモバイルユーザーへのフロー6の方向は、一方のサイドが接続の観点から通信を開始することを示します。

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>使用例: Office 365 トランク経由でのチームと PSTN

Office 365 には、公衆交換電話網 (PSTN) での通話の発信と受信を可能にする電話システムがあります。 PSTN トランクが電話システムの通話プランを使って接続されている場合、このユースケースには特別な接続要件はありません。 (独自のオンプレミス PSTN トランクを Office 365 に接続する場合は、電話システムのダイレクトルーティングを使うことができます)。

[![Microsoft Teams Online の通話フロー図08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*図 8-Office 365 トランク経由のチーム間の PSTN*

#### <a name="use-case-teams-meeting"></a>使用例: Teams 会議

音声/ビデオ/画面共有 (VBSS) 会議サーバーは、Office 365 に含まれています。 これには、顧客ネットワークから到達可能である必要があり、Nomadic Cloud クライアントから到達可能である必要があるパブリック IP アドレスが含まれています。 クライアント/エンドポイントごとに、会議サーバーに接続できるようにする必要があります。

内部クライアントでは、1対1の通話の場合と同じ方法で、ローカル、再帰、およびリレーの候補が取得されます。 クライアントは、招待状にこれらの候補を会議サーバーに送信します。 会議サーバーは、公開された IP アドレスを持っているため、relay を使用しません。そのため、ローカル IP アドレス候補で応答します。 クライアントと会議サーバーは、1対1の通話の場合と同じ方法で接続性を確認します。

次の点に注意してください。

- Teams クライアントは Skype for Business 会議に参加できず、Skype for Business クライアントは Teams 会議に参加できません。

- PSTN ユーザーは、会議の開催者の PSTN 通話や会議のプロビジョニングに応じて、"ダイヤルイン" または "ダイヤルアウト" を行うことができます。

- ゲストユーザーまたはお客様のユーザーがゲストプライベートネットワークから参加できる場合があります。これは、厳密な規則で FW/NAT を使用して保護されています。

[![Microsoft Teams Online の通話フロー図09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*図 9-Teams 会議*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>使用例: オンプレミスの Skype for Business とのフェデレーション

**Office 365 で Teams トランスポートリレーによって中継されるメディア**

[![Microsoft Teams Online の通話フロー図10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*図 10-Office 365 で Teams トランスポートリレーによって中継されるメディア*

次の点に注意してください。

- フェデレーションとは、2つのテナント間の通信を定義することです。 この場合、federates を使用するテナント A は、オンプレミスの Skype for Business を使用するテナント B と共に使用されます。 テナント B でも Office 365 を使用している場合、Skype for Business クライアントでは、フロー3を使って Office 365 に接続していました。

- フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for business Server へのシグナルおよびメディアは、このドキュメントの範囲外です。 ただし、わかりやすくするために、ここで示しています。

- チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。

- このケースのメディアは、Office 365 の Teams トランスポートリレーによって、フロー4を使って顧客ネットワークとリモートの Skype for Business クライアントに中継されます。

**フェデレーションテナントでの Skype for Business メディアリレーによるメディアの中継**

[![Microsoft Teams Online の通話フロー図11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*図 11-フェデレーションされたテナントでの Skype for Business メディアリレーによるメディアの中継*

次の点に注意してください。

- フェデレーションされた Skype for Business クライアントから社内の Skype for business Server へのシグナリングとメディアは、このドキュメントの範囲外です。 ただし、わかりやすくするために、ここで示しています。

- チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。

- このケースのメディアは、フロー2を使って、Skype for Business のオンプレミスメディアリレーによって、お客様のネットワークに中継されます。 (Teams ユーザーからフェデレーションされた顧客ネットワークでのリモートメディアリレーへのトラフィックは、逆方向のトラフィックが流れるまでに、最初にメディアリレーによってブロックされることに注意してください)。 ただし、双方向フローは両方の方向に接続を開きます。)

**Direct (ピアツーピア)**

[![Microsoft Teams Online の通話フロー図12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*図 12-直接 (ピアツーピア)*

### <a name="teams-hybrid-topology"></a>Teams ハイブリッドトポロジ

このトポロジには、Skype for Business のオンプレミス展開を含む Teams が含まれています。

[![Microsoft Teams Online の通話フロー図13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*図 13-Teams ハイブリッドトポロジ*

- 上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。 メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。

- Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。

追加のフロー (チームトポロジの一番上):

- **フロー 5a** –顧客ネットワーク内の Teams ユーザーと、顧客ネットワーク edge での Skype for business のオンプレミスメディアリレーとの間のピアツーピアメディアフローを表します。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>ユースケース: チームと Skype for Business の一対一

**顧客ネットワーク内のハイブリッド**

[![Microsoft Teams のオンライン通話フロー図14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*図 14-顧客ネットワーク内のハイブリッド*

チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。 ただし、メディアは、フロー5を使って顧客のネットワーク内で直接ピアツーピアにルーティングされます。

**外部の Skype for Business ユーザーとのハイブリッド顧客ネットワーク– Office 365 によって中継される**

[![Microsoft Teams Online の通話フロー図15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*図 15-外部の Skype for Business ユーザーとのハイブリッド顧客ネットワーク (Office 365 による中継)*

次の点に注意してください。

- Skype for Business クライアントからオンプレミスの Skype for Business Server へのシグナリングとメディアは、このドキュメントの範囲外です。 ただし、わかりやすくするために、ここで示しています。

- チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。

- メディアは、Office 365 の Teams トランスポートリレーを通じて、フロー4経由で顧客ネットワークに中継されます。

**外部の Skype for Business ユーザーを使用したハイブリッド顧客ネットワーク-オンプレミスエッジによる中継**

[![Microsoft Teams Online の通話フロー図16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*図 16-外部の Skype for Business ユーザーを使用したハイブリッド顧客ネットワーク-オンプレミスエッジによる中継*

次の点に注意してください。

- Skype for Business クライアントからオンプレミスの Skype for business Server へのシグナリングとメディアは、このドキュメントの範囲外です。 ただし、わかりやすくするために、ここで示しています。

- シグナリングは、Office 365 のゲートウェイでブリッジされます。

- メディアは、Skype for Business オンプレミスエッジ内の skype for Business メディアリレーによって、メディアフロー5A を使用して、顧客ネットワーク内の Teams ユーザーに中継されます。

### <a name="teams-with-phone-system-direct-routing-topology"></a>電話システムのダイレクトルーティングトポロジを使用しているチーム

このトポロジには、電話システムのダイレクトルーティングを行うチームが含まれます。

ダイレクトルーティングでは、サポートされているオンプレミスのユーザー所有のセッションボーダーコントローラー (SBC) ハードウェアデバイスを Office 365 にペアリングし、テレフォニートランクを接続することで、サードパーティの公衆交換電話網 (PSTN) サービスプロバイダーを使用することができます。そのデバイス。

このシナリオをサポートするには、お客様は Microsoft 認定パートナーの1つから直接ルーティングするための認定された SBC を展開する必要があります。 SBC は、ベンダーによって推奨されるように構成する必要があります。また、直接 UDP トラフィック用に Office 365 からルーティングすることもできます。 メディアは、Teams から直接、または Skype for Business クライアントから SBC (Teams のゲートウェイを経由しない) に、または Teams のゲートウェイを通過する場合があります。 樹幹が Teams ゲートウェイをバイパスするように構成されている場合、SBC を使った接続は氷に基づいています。 SBC は ICE をサポートしていますが、Teams/Skype for Business media endpoint は ice Full フォームをサポートしています。

[![Microsoft Teams Online の通話フロー図17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* 図 17-電話システムのダイレクトルーティングトポロジを使用したチーム

次の点に注意してください。

- 上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。 メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。

- Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。

追加のフロー (Teams online トポロジの一番上):

- **Flow 4 '** -Office 365 から顧客ネットワークへのフローを表します。これを使用して、お客様は、クラウドの Teams メディアサーバーと SBC オンプレミスの間の接続を確立します。
- **Flow 5b** –お客様のネットワーク内の Teams ユーザー間のメディアフローを表します。
- **フロー 5c** – PSTN 転送 call バイパスモードで、ダイレクトルーティングの sbc と別のダイレクトルーティングの sbc 間のメディアフローを表します。

**直接ルーティングを使用する内部ユーザー (Office 365 で Teams トランスポートリレーによって中継されるメディア)**

[![Microsoft Teams Online の通話フロー図18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*図 18-直接ルーティングを使用する内部ユーザー (Office 365 で Teams トランスポートリレーによって中継されたメディア)*

次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびメディアの場合は、flow 4 または flow 4 を使います。

- 顧客ネットワーク内のクライアントから Office 365 へのシグナリングとメディアの送信は、flow 4 を使います。

**直接ルーティングを使用するリモートユーザー (メディアは、Office 365 でメディアサーバー (MP) 経由でルーティングされます)**

[![Microsoft Teams Online の通話フロー図19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*図 19-直接ルーティングを使用しているリモートユーザー (メディアは、Office 365 でメディアサーバー (MP) 経由でルーティングされます)*

次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびメディアの場合は、flow 4 または flow 4 を使います。

- インターネット上のクライアントから Office 365 へのシグナリングとメディアの流れ3を使用します。

**内部ユーザー直接ルーティング (メディアバイパス)**

[![Microsoft Teams Online の通話フロー図20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*図 20-内部ユーザー直接ルーティング (メディアバイパス)*

次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 およびその逆のシグナリングでは、flow 4 またはフロー4のどちらか一方または両方を使用します。

- 顧客ネットワーク内のクライアントから Office 365 へのシグナリングは、flow 4 を使います。

- 顧客ネットワーク内のクライアントから、顧客ネットワーク内の SBC までのメディア。フロー5B を使用します。

**直接ルーティングを使用するリモートユーザー (Office 365 の Teams トランスポートリレーによって中継されたメディアのバイパス)**

[![Microsoft Teams Online の通話フロー図21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*図 21-直接ルーティングを使用するリモートユーザー (Office 365 の Teams トランスポートリレーによって中継されるメディア)*

次の点に注意してください。

- SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。

- インターネット上のクライアントから Office 365 への通知では、flow 3 が使用されます。

- インターネット上のクライアントからお客様のネットワーク内の SBC へのメディアは、フロー3と4を使い、Office 365 の Teams トランスポートリレーによって中継されます。

**リモートユーザーの直接ルーティング (メディアバイパスダイレクト)**

[![Microsoft Teams Online の通話フロー図22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*図 22-リモートユーザーの直接ルーティング (メディアバイパスダイレクト)*

次の点に注意してください。

- SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。

- インターネット上のクライアントから Office 365 への通知では、flow 3 が使用されます。

- インターネット上のクライアントから顧客ネットワーク内の SBC までのメディアは、フロー2を使用します。

**直接ルーティング (メディアバイパス) – PSTN 転送通話 (通話転送/転送のため)**

[![Microsoft Teams Online の通話フロー図23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*図 23-直接ルーティング (メディアバイパス)-PSTN 転送通話 (通話転送/転送のため)*

次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。

- クライアントは、通話が PSTN から PSTN に hairpinned された後に、シグナリングおよびメディアループを終了します。

- 顧客ネットワーク内の SBC インスタンス A から、顧客ネットワーク内の SBC インスタンス B へのメディア (場所 A と B は同じインスタンスである可能性があります) は、フロー5C を使用します。

**直接ルーティング (Office 365 経由のメディア) –2つのテナント間での PSTN 転送通話**

[![Microsoft Teams Online の通話フロー図24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*図 24-ダイレクトルーティング (Office 365 経由のメディア) –2つのテナント間での PSTN 転送通話*

次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。

- クライアントは、通話が PSTN から PSTN に hairpinned された後に、シグナリングおよびメディアループを終了します。

- 顧客ネットワーク X から SBC インスタンス B 内の SBC インスタンスからのメディアは、Office 365 メディアサーバーを通じて中継され、バイパスモードは使用できません。

## <a name="teams-with-express-route-optimization"></a>エクスプレスルートの最適化を使用しているチーム

[![Microsoft Teams Online の通話フロー図25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*図 25-簡易ルートの最適化を使用したチーム*

エクスプレスルートが両端揃えで展開されている場合、チームフローはフロー4からフロー1に、フロー4からフロー1に再ルーティングすることができます。 ただし、Teams アプリケーションは、フロー4と4を使って、インターネット経由で他の Office 365 フローに対して困難な依存関係を持っています。そのため、これらのフローはブロックしないでください。

Skype for Business ハイブリッドエッジトラフィックは、インターネットにルーティングされるため、外部ユーザーと通信したり、他のテナントとフェデレーションを行ったりすることはできません。

非対称のフローを防ぐために、再ルーティングは両方の方向で行われる必要があります。 つまり、顧客ネットワーク内のアドレスは、インターネットまたはエクスプレスルート (最適化に基づく) を介してルーティングされますが、両方を経由することはできません。


**外部ユーザーに対する顧客ネットワーク (メディアトランスポートリレーによって中継されるメディア):**

[![Microsoft Teams Online の通話フロー図26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*図 26-外部ユーザーへの顧客ネットワーク (Teams トランスポートリレーによるメディアの中継)*

**高レベルの手順:**

1. 顧客ネットワーク内の Teams ユーザーは、flow2 を使って URL ドメイン名 (DNS) を解決します。
1. 顧客ネットワーク内の teams ユーザーは、フロー1を使用して Teams トランスポートリレーにメディアリレーポートを割り当てます。
1. 顧客ネットワーク内の Teams ユーザーは、flow 1 から Office 365 への "招待" を、ICE 候補と共に送信します。
1. Office 365 はフロー3を使って外部 Teams ユーザーに通知を送信します。
1. Teams の外部ユーザーは、flow 3 を使用して Teams トランスポートリレーにメディアリレーポートを割り当てます。
1. Teams の外部ユーザーはフロー3を使って氷の候補で "answer" を送信します。フロー1を使って Teams ユーザー A に戻されます。
1. Teams ユーザー A と Teams ユーザー B は、ICE 接続テストを呼び出し、フロー1と3を選択します。これは、Office 365 の Teams トランスポートリレーによって中継されます。
1. Teams ユーザーは、フロー1と3を使用して、Office 365 にテレメトリを送信します。

> [!NOTE]
> フロー4は、フロー4を設定する他のマイクロサービスで Teams アプリケーションの依存関係をサポートするために有効にする必要があります。
