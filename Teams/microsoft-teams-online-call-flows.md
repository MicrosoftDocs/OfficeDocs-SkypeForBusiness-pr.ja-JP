---
title: Microsoft Teams の通話フロー
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: Teams で Office 365 のフローがさまざまなトポロジで使用される方法について説明します。
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232160"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams の通話フロー

> [!Tip]
> Teams でのネットワークの活用方法と最適なネットワーク接続を計画する方法については、次のセッションをご覧ください: [Teams のネットワーク計画](https://aka.ms/teams-networking)

## <a name="overview"></a>概要
この記事では、Teams で Office 365 の通話フローがさまざまなトポロジで使用される方法について説明します。 また、ピアツーピアのメディア コミュニケーションで使用される固有の Teams のフローについても説明します。 この記事では、これらのフロー、その目的、ネットワーク上でのフローの始端と終端について説明します。 この記事では次のことを想定しています。

- Flow X は、オンプレミスの Office 365 クライアントがクラウドの Office 365 サービスと通信するために使用します。 これは、顧客ネットワークが始端となり、Office 365 のエンドポイントとして終端します。

- フロー Y は、Office 365 が依存しているインターネット上のサービスと通信するためにオンプレミスの Office 365 クライアントによって使用されます。 これは、顧客ネットワークが始端となり、インターネットのエンドポイントとして終端します。

このトピックには次のセクションが含まれます。

- **背景** - Office 365 フローが通過する可能性があるネットワーク、トラフィックの種類、顧客のネットワークから Office 365 のサービス エンドポイントへの接続に関するガイダンス、サードパーティ製のコンポーネントとの相互運用性、Teams がメディア フローの選択に使用する原則などの背景情報を提供します。

- **さまざまなトポロジでの通話フロー** - さまざまなトポロジでの通話フローの使用例を示します。 このセクションでは、各トポロジについて、サポートされるすべてのフローを列挙し、これらのフローの使用方法をいくつかのユース ケースを使って示します。 各ユース ケースについて、フローの順序とセクションをフローの図を用いて示します。 

- **Express Route による Teams の最適化** - 最適化のために Express Route が展開された場合にこれらのフローがどのように使用されるかを、単純なトポロジを用いて説明します。

## <a name="background"></a>背景
### <a name="network-segments"></a>ネットワーク セグメント
**顧客ネットワーク**: これは、管理者が制御および管理するネットワーク セグメントです。 これには、顧客のオフィス内の有線または無線によるすべての顧客の接続、オフィスビル間の接続、オンプレミス データセンターへの接続に加え、インターネット プロバイダー、ExpressRoute、またはプライベート ピアリングへの接続が含まれます。 

通常、顧客ネットワークには、ファイアウォールおよび/またはプロキシサーバーを使用して組織のセキュリティポリシーを適用するネットワーク境界が複数あり、設定と構成を行った特定のネットワーク トラフィックのみが許可されるようになっています。 このネットワークの管理を行うのは管理者であるため、管理者はネットワークのパフォーマンスを直接管理できます。ネットワーク上のサイトとネットワークから Office 365 ネットワークの接続の両方のパフォーマンスについて、ネットワーク評価を行うことを強くお勧めします。 

**インターネット**: これはネットワーク全体の一部で、顧客ネットワークの外部から Office 365 に接続するユーザーによって使用されるネットワーク セグメント。 また、顧客ネットワークから Office 365 への一部のトラフィックにも使用されます。 

**訪問先 / ゲスト ネットワーク**: 顧客ネットワークの外部にある、ユーザーおよび/またはそれらのユーザーのゲストが訪問することができるネットワーク セグメントで、公衆インターネットには含まれません。 たとえば、Teams のサービスを操作するユーザーおよび/またはそれらのユーザーの顧客が利用する、Teams が展開されていない家庭のプライベート ネットワークや企業のプライベート ネットワークなどを含みます。

>**注**: Office 365 への接続は、これらのネットワークにも適用されます。

**Office 365**: これは、Office 365 サービスをサポートするネットワーク セグメントです。 これは世界中に分散しているネットワークで、ほとんどの場所で顧客ネットワークに近接するエッジを使用しています。 この記事で取り扱う機能には、トランスポート リレー、会議サーバー、メディア プロセッサが含まれます。 

**Express Route (オプション)**: これはネットワーク全体の一部で、Office 365 ネットワークへの専用のプライベート接続を提供するネットワーク セグメントです。

### <a name="types-of-traffic"></a>トラフィックの種類

**リアルタイム メディア**: オーディオ、ビデオ、および画面共有のワークロードをサポートする RTP (リアルタイム転送プロトコル) 内にカプセル化されたデータ。 一般的に、メディア トラッフィックは遅延に対して非常に敏感なため、このトラフィックはできるだけ直接的な経路を使用し、トランスポート層プロトコルとして TCP ではなく、品質の点で対話的なリアルタイム メディアには最良のトランスポートである UDP を使用します。 (注: 最後の手段として、メディアには TCP/IP を使用し、HTTP プロトコル内でトンネリングすることができますが、品質に悪影響を与える可能性があるため、お勧めできません)。RTP フローは SRTP を介して保護され、ペイロードのみが暗号化されます。

**シグナリング**: クライアントとサーバーまたはその他のクライアントとの間の通信リンクで、アクティビティ (たとえば、通話が開始された場合など) の制御とインスタント メッセージの配信に使用されます。 ほとんどのシグナリング トラフィックは HTTPS ベースの REST インターフェイスを使用しますが、一部の シナリオ (Office 365 とセッション ボーダー コントローラーの間の接続など) では、SIP プロトコルを使用します。 このトラフィックは遅延に対してあまり敏感ではありませんが、エンドポイント間に数秒を超える遅延があった場合、サービス停止や通話のタイムアウトが発生する可能性がある点にご注意ください。 

### <a name="connectivity-to-office-365"></a>Office 365 への接続

Teams を使用するには、[インターネットへの接続が必要です](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。 Teams のエンドポイントの URL と IP アドレスの範囲は、「[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」に記載されています。 (注: TCP ポート 80 および 443、UDP ポート 3478〜3481 へのオープン接続が必要です。) さらに、Teams は Skype for Business Online に依存しているため、Skype for Business Online もインターネットに接続されている必要があります。

Teams のメディア フロー接続は、標準の IETF ICE (Interactive Connectivity Establishment) の手順を通して実装されます。

### <a name="interoperability-restrictions"></a>相互運用性の制限
**サードパーティのメディア リレー**: Teams のメディア フロー (つまり、いずれかのメディア エンドポイントが Teams である場合) は、Teams または Skype for Business のネイティブ メディア リレーのみを通過できます。 サードパーティ製メディア リレーとの相互運用性は、サポートされていません。 (注: PSTN との境界にあるサードパーティの SBC は、RTP/RTCP ストリーム を終了し、SRTP を介して保護されている必要があり、次のホップにリレーさせることはできません)。

**サードパーティの SIP プロキシ サーバー**: サードパーティの SBC および/またはゲートウェイを使用する Teams のシグナリング SIP ダイアログは、 Teams または Skype for Business のネイティブ SIP プロキシを通過できます。 サードパーティ製 SIP プロキシとの相互運用性は、サポートされていません。

**サードパーティの B2BUA (つまり、SBC)**: PSTN との間の Teams のメディア フローは、サードパーティの SBC により終端されます。 ただし、Teams ネットワーク内のサードパーティーの SBC との相互運用性 (つまり、サードパーティの SBC が Teams と Skype for Business の 2 つのエンドポイントを仲介) はサポートされていません。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Microsoft Teams で推奨されないテクノロジ

**VPN ネットワーク**: メディア トラフィック (フロー 2 に該当) に使用することはお勧めしません。 https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/ で指定されるように、VPN クライアントはスプリット VPN を使用し、外部の 非 VPN ユーザーなどのメディア トラフィックをルーティングする必要があります。

>**注**: 題名は Lync となっていますが、Teams にも適用できます。

**パケット シェーパー**: あらゆる種類のパケット スニッパー、パケット検査、またはパケット シェーパーのデバイスの使用はお勧めしません。品質が大きく低下する場合があります。 

### <a name="principles"></a>原則
Microsoft Teams の通話フローを理解するのに役立つ、4つの一般的な原則があります。
 
1.  Microsoft Teams の会議は、最初の参加者が参加したのと同じ地域の Office 365 によってホストされます。 (注: トポロジによってこのルールの例外が発生する場合については、記事で説明します。適切な通話フローも示されます。)

2.  Office 365 の Teams メディア エンドポイントは、通話の種類に基づいてではなく、メディア処理のニーズに基づいて使用されます。 (たとえば、ポイントツーポイントの通話では、トランスクリプションおよび/または録音のためのメディア処理に、クラウド内のメディア エンドポイントを使用する場合がありますが、参加者が 2 人の会議ではクラウド内のメディア エンドポイントを使用しない場合があります。) ただし、ほとんどの会議では、ミキシングおよびルーティングのために、会議がホストされる場所に割り当てられているメディア エンドポイントが使用されます。 クライアントからメディア エンドポイントに送信されるメディア トラフィックは、直接ルーティングされる場合と、顧客ネットワークのファイアウォール制限のために必要な場合は、Office 365 のトランスポート リレーを使用する場合とがあります。 

3.  ピアツーピア通話のメディア トラフィックは、通話でクラウド内のメディア エンドポイントが要求されていない限り (上の項目 2 を参照)、使用できる最も直接的なルートを使用します。 リモート ピア (クライアント) への直接のルートが優先されますが、このルートが利用できない場合は、1 つまたは複数のトランスポート リレーがトラフィックを中継します。 メディアの品質に影響を与えるため、メディア トラフィックがパケット シェーパーや VPN サーバーなどのサーバーを通過しないことが推奨されます。

4.  シグナリング トラフィックは、常にユーザーに最も近いサーバーに送信されます。 

選択されるメディア パスの詳細については、「https://www.youtube.com/watch?v=1tmHMIlAQdo」を参照してください。

## <a name="call-flows-in-various-topologies"></a>さまざまなトポロジにおける通話フロー
### <a name="teams-topology"></a>Teams のトポロジ
このトポロジは、Skype for Business Server や電話システムのダイレクト ルーティングなどのオンプレミスの展開がない状態でクラウドから Teams のサービスを利用するお客様に使用されます。 また、Office 365 のインターフェイスは、Azure Express Route を使用せずにインターネット経由で実行されます。 

[![Microsoft Teams オンライン通話フロー 図 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*図 1 - Teams のトポロジ*

次の点に注意してください。

- 上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。 メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。
- Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。

次のオプションのトポロジの詳細については、この記事の後の方で説明します。

- Skype for Business のオンプレミスの展開については、「**Teams ハイブリッド トポロジ**」を参照してください。
- 電話システムのダイレクト ルーティング (PSTN 接続用) については、「**電話システムのダイレクト ルーティングを使用する Teams のトポロジ**」を参照してください。
- Express Route については、「**Express Route による Teams の最適化**」を参照してください。

**フローの説明**
- **フロー 2** – ユーザーが、Teams の操作の一部として顧客ネットワーク上で開始するインターネットへのフローを表します。 この種類のフローの例は、DNS とピアツーピア メディアです。
- **フロー 2'** – Teams のリモート モバイル ユーザーが VPN を使用して開始する顧客ネットワークへフローを表します。 
- **フロー 3** – Teams のリモート モバイル ユーザーが開始する Office 365/Teams のエンドポイントへのフローを表します。 
- **フロー 4** – 顧客ネットワーク上のユーザーが開始する Office 365/Teams のエンドポイントへのフローを表します。
- **フロー 5** – Teams ユーザーと別の Teams ユーザーまたは顧客ネットワーク内の Skype for Business ユーザーの間のピアツーピア メディア フローを表します。
- **フロー 6** – Teams のリモート モバイル ユーザーと別の Teams のリモート モバイル ユーザーまたは Skype for Business ユーザーの間の、インターネットを介したピアツーピア メディア フローを表します。

#### <a name="use-case-one-to-one"></a>ユース ケース: 一対一
一対一の通話では共通のモデルが使用され、発信者は、ローカル、リレー、および再帰 (リレーから見える、クライアントのパブリック IP アドレス) の候補を含む、IP アドレス/ポートから成る候補のセットを取得します。 発信者は、これらの候補を通話相手に送信します。通話を受けた相手は、同様の候補のセットを取得し、それを発信者に送信します。 STUN 接続確認メッセージは、発信者/受信者のメディア パスはどれが機能しているかを判断し、機能しているパスの中から最適のもの選択します。 その後、選択された候補のペアを使用してメディア (つまり、SRTP を介して保護された RTP/RTCP パケット) が送信されます。 トランスポートリレーは、 Office 365 の一部として展開されます。

ローカル IP アドレス/ポートの候補または再帰候補に接続がある場合、クライアント間のダイレクト パス (または NAT 経由) がメディア用に選択されます。 クライアントが両方とも顧客ネットワーク上にいる場合は、ダイレクト パスが選択されるはずです。 これには、顧客ネットワーク内での UDP への直接接続が必要です。 クライアントが両方とも Nomadic Crowd のユーザーである場合、NAT/ファイアウォールによっては、メディアは直接接続を使用する可能性があります。

一方のクライアントが顧客ネットワーク内にいて、もう一方のクライアントが外部にいる (モバイル クラウド ユーザーなど) 場合、ローカル候補と再帰候補の間の直接接続は正常に機能しません。 この場合、どちらかのクライアントが、トランスポート リレー候補のいずれかを使用するというオプションがあります (たとえば、内部のクライアントが Office 365 のトランスポート リレーからリレー候補を取得した場合は、外部のクライアントは STUN/RTP/RTCP パケットをトランスポート リレーに送信できる必要があります)。 別のオプションとして、内部のクライアントが、モバイル クラウド クライアントが取得したリレー候補に送信するというものです。 メディアの場合は UDP 接続を強く推奨しますが、TCP もサポートされています。

**大まかな手順**:
1. Teams ユーザー A が、フロー 2 経由で URL ドメイン名 (DNS) を解決します。
2. Teams ユーザー A が、フロー 4 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。
3. Teams ユーザー A が、フロー 4 経由で "招待状" を ICE 候補と共に Office 365 に送信します。
4. Office 365 が、フロー 4 経由で Teams ユーザー B に通知を送信します。
5. Teams ユーザー B が、フロー 4 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。
6. Teams ユーザー B が、フロー 4 経由で "回答" を ICE 候補と共に送信し、これはフロー 4 経由で Teams ユーザー A に再び転送されます。
7. Teams ユーザー A および Teams ユーザー B が ICE 接続テストを実行し、最適なメディア パスが選択されます (下の図でさまざまなユース ケースをご覧ください)。
8. Teams ユーザーが、フロー4 経由でテレメトリを Office 365 に送信します。

**顧客ネットワーク内:**

[![Microsoft Teams オンライン通話フロー 図 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*図 2 - 顧客ネットワーク内*
 
手順 7 では、ピアツーピア メディア フロー 5 が選択されています。
 
メディアは双方向です。 フロー 5 の方向は、この記事のすべてのフローの場合と同様、一方が通信を開始したことを接続の観点から示します。 このケースでは両方のエンドポイントが顧客ネットワーク内にあるため、使用されている方向を考慮する必要がありません。

**顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):**

[![Microsoft Teams オンライン通話フロー 図 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*図 3 - 顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):*
 
手順 7 では、フロー 4 (顧客ネットワークから Office 365) とフロー 3 (Teams リモート モバイル ユーザーから Office 365) が選択されています。 これらのフローは、Office 365 内の Teams トランスポート リレーにより中継されます。

メディアは双方向で、どちら側が通信を開始したかを接続の観点から示します。 この場合、これらのフローは、異なるトランスポート プロトコルとアドレスを使用して、シグナリングとメディアに使用されます。

**顧客ネットワークから外付ユーザーへ (ダイレクト メディア):**

[![Microsoft Teams オンライン通話フロー 図 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*図 4 - 顧客ネットワークから外部ユーザーへ (ダイレクト メディア)*
 
手順 7 では、顧客ネットワークから インターネット (クライアントのピア) のフロー 2 が選択されています。
- モバイル ユーザー (Office 365 経由では中継されていないという意味) とのダイレクト メディアは省略可能です。 Office 365 のトランスポート リレー経由のパスを強制するために、顧客はこのパスをブロックできることを意味します。

- メディアは双方向です。 モバイル ユーザーへのフロー 2 の方向は、一方が通信を開始したことを接続の観点から示します。 

**VPN から内部ユーザーへ (メディアは Teams トランスポート リレーが中継)**

[![Microsoft Teams オンライン通話フロー 図 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*図 5 - VPN から内部ユーザーへ (メディアは Teams トランスポート リレーが中継)*
 
VPN と顧客ネットワークとの間のシグナリングは、フロー 2 経由で行われます。 顧客ネットワークと Office 365 との間のシグナリングは、フロー 4 経由で行われます。 ただし、メディアは VPN をバイパスし、Office 365 の Teams メディア リレーを介してフロー 3 とフロー 4 経由でルーティングされます。

**VPN ユーザーから内部ユーザーへ (ダイレクトメディア)**

[![Microsoft Teams オンライン通話フロー 図 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*図 6 - VPN ユーザーから内部ユーザーへ (ダイレクトメディア)*

VPN と顧客ネットワークとの間のシグナリングは、フロー 2 経由で行われます。 顧客ネットワークと Office 365 との間のシグナリングは、フロー 4 経由で行われます。 ただし、メディアは VPN をバイパスし、フロー 2 (顧客ネットワークからインターネット) 経由でルーティングされます。

メディアは双方向です。 モバイル ユーザーへのフロー 2 の方向は、一方が通信を開始したことを接続の観点から示します。

**VPN ユーザーから外部ユーザーへ (ダイレクトメディア)**

[![Microsoft Teams オンライン通話フロー 図 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*図 7 - VPN ユーザーから外部ユーザーへ (ダイレクトメディア)*

VPN からのシグナリングは、顧客ネットワークへはフロー 2' 経由で、Office 365 へはフロー 4 経由で行われます。 ただし、メディアは VPN をバイパスし、フロー 6 経由でルーティングされます。

メディアは双方向です。 モバイル ユーザーへのフロー 6 の方向は、一方が通信を開始したことを接続の観点から示します。

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>ユース ケース: Office 365 トランク経由で Teams から PSTN へ
Office 365 には、公衆交換電話網 (PSTN) を使用して通話を発信および受信できる電話システムがあります。 PSTN トランクが電話システムの通話プラン経由で接続されている場合、このユース ケースに関しては特別な接続要件はありません。 (自社のオンプレミスの PSTN トランクを Office 365 に接続する場合は、電話システムのダイレクト ルーティングを使用できます。)

[![Microsoft Teams オンライン通話フロー 図 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*図 8 - Office 365 トランク経由で Teams から PSTN へ*

#### <a name="use-case-teams-meeting"></a>ユースケース: チーム会議

音声/ビデオ/画面共有 (VBSS) 会議サーバーは、Office 365 の一部です。 これには顧客ネットワークから到達可能である必要があるパブリック IP アドレスが含まれ、これは、Nomadic Cloud のクライアントから到達可能である必要があります。 各クライアント/エンドポイントは、会議サーバーに接続できる必要があります。

内部クライアントは、一対一の通話で説明したのと同じ方法でローカル、再帰、およびリレー候補を取得します。 クライアントは、招待状にある会議サーバーにこれらの候補を送信します。 会議サーバーは、公開されている IP アドレスを持っているためにリレーを使用しません。そのため、会議サーバーのローカル IP アドレス候補が返されます。 クライアントと会議サーバーは、一対一の通話で説明したのと同じ方法で接続を確認します。 

次の点に注意してください。

- Teams のクライアントは Skype for business 会議に参加できず、Skype for Business のクライアントは Teams 会議に参加できません。

- PSTN ユーザーは、会議開催者の PSTN 通話および/または会議のプロビジョニングに応じて、"ダイヤル イン" または "ダイヤル アウト" することもできます。 

- ゲスト ユーザーまたは顧客ユーザーはゲスト プライベートネットワークに参加できます。このネットワークは、厳密なルールを適用して FW/NAT を介して保護されています。

[![Microsoft Teams オンライン通話フロー 図 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*図 9 - Teams 会議*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>ユース ケース: Skype for Business オンプレミス とのフェデレーション

**Office 365 内の Teams トランスポート リレーにより中継されるメディア**

[![Microsoft Teams オンライン通話フロー 図 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*図 10 - Office 365 内の Teams トランスポート リレーにより中継されるメディア*

次の点に注意してください。

- フェデレーションは、その性質上、2 つのテナント間の通信です。 この例では、Teams を使用する テナント A は、Skype for Business オンプレミスを使用するテナント B とフェデレーションします。 もしテナント B も Office 365 を使用していた場合は、Skype for Business クライアントは Office 365 との接続にフロー 3 を使用していたはずです。

- フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、 説明をわかりやすくするためにこれを図に示します。

- Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。

- メディアはこの場合、Office 365 内の Teams トランスポート リレーにより、フロー 4 経由で Skype for Business クライアントに中継されます。

**フェデレーションされたテナントの Skype for Business メディア リレーによって中継されるメディア**

[![Microsoft Teams オンライン通話フロー 図 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*図 11 - フェデレーションされたテナントの Skype for Business メディア リレーによって中継されるメディア*

次の点に注意してください。

- フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、 説明をわかりやすくするためにこれを図に示します。

- Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。

- メディアはこの場合、Skype for Business オンプレミス メディア リレーにより、フロー 2 経由で顧客ネットワークに中継されます。 (フェデレーションされた顧客ネットワークのリモート メディア リレーへ Teams ユーザーからのトラフィックは、逆方向のトラフィックが流れ始めるまで、メディアリレーによって最初はブロックされます。 ただし、双方向フローは、双方向の接続を開きます)。

**直接 (ピアツーピア)**

[![Microsoft Teams オンライン通話フロー 図 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*図 12 - 直接 (ピアツーピア)*

### <a name="teams-hybrid-topology"></a>Teams ハイブリッド トポロジ
このトポロジには、Skype for Business のオンプレミス展開を使用する Teams が含まれます。

[![Microsoft Teams オンライン通話フロー 図 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*図 13 - Teams ハイブリッド トポロジ*
 
- 上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。 メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。

- Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。

その他のフロー (Teams のトポロジへの追加)
- **フロー 5 A** – 顧客ネットワーク内の Teams ユーザーと、顧客ネットワークのエッジにある Skype for Business オンプレミス メディア リレーとの間の、ピアツーピアのメディア フローを表します。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>ユース ケース: Teams から Skype for Business へ、一対一
**顧客ネットワーク内のハイブリッド**

[![Microsoft Teams オンライン通話フロー 図 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*図 14 - 顧客ネットワーク内のハイブリッド*
 
Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。 ただし、メディアは顧客ネットワーク内で、フロー 5 経由でピアツーピアに直接ルーティングされます。

**ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (Office 365 により中継)**

[![Microsoft Teams オンライン通話フロー 図 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*図 15 - ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (Office 365 により中継)*

次の点に注意してください。

- Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、 説明をわかりやすくするためにこれを図に示します。

- Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。

- メディアは、Office 365 内の Teams トランスポート リレーを通して、フロー 4 経由で顧客ネットワークに中継されます。

**ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (オンプレミス エッジ により中継)**

[![Microsoft Teams オンライン通話フロー 図 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*図 16 - ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (オンプレミス エッジ により中継)*
 
次の点に注意してください。

- Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、 説明をわかりやすくするためにこれを図に示します。

- シグナリングは、Office 365 のゲートウェイによってブリッジされます。

- メディアは、Skype for Business オンプレミス エッジ内の Skype for Business メディア リレーにより、フロー 5A 経由で顧客ネットワーク内の Teams ユーザーに中継されます。

### <a name="teams-with-phone-system-direct-routing-topology"></a>電話システムのダイレクト ルーティングを使用する Teams のトポロジ
このトポロジには、電話システムのダイレクト ルーティングを使用する Teams が含まれます。 

ダイレクト ルーティングを使用すると、サポートされている顧客が所有するオンプレミスのセッション ボーダー コントローラー (SBC) 機器デバイスを Office 365 にペアリングし、次にテレフォニー トランクをそのデバイスに接続することにより、公衆交換電話網 (PSTN) のサードパーティ サービス プロバイダーを利用できるようになります。 

このシナリオをサポートするには、顧客は、Microsoft の認定パートナーのいずれかによりダイレクト ルーティング用に認定された SBC を展開する必要があります。 SBC は製造元の推奨通りに構成する必要があり、Office 365 からのダイレクト UDP トラフィックがルーティング可能である必要があります。 メディアは、Teams クライアントおよび/または Skype for Business クライアントから (Teams ゲートウェイをバイパスして) SBC に直接流れることも、Teams ゲートウェイを通過することもできます。 トランクが Teams ゲートウェイをバイパスするように構成されている場合は、SBC との接続は ICE に基づきます。SBC では ICE-Lite がサポートされ、Teams/Skype for Business のメディア エンドポイントでは ICE Full がサポートされます。 

[![Microsoft Teams オンライン通話フロー 図 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*図 17 - 電話システムのダイレクト ルーティングを使用する Teams のトポロジ

次の点に注意してください。

- 上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。 メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。

- Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。

その他のフロー (Teams のトポロジへの追加):
- **フロー 4'** - クラウド内の Teams メディア サーバーとオンプレミスの SBC との間の接続を確立するために使用される、Office 365 から顧客ネットワークへのフローを表します。
- **フロー 5B** - バイパス モードでの、顧客ネットワーク内の Teams ユーザーとダイレクト ルーティング SBC のメディア フローを表します。
- **フロー 5C** – PSTN ヘアピン コール バイパス モードでの、ダイレクト ルーティング SBC と別のダイレクト ルーティング SBC と間のメディア フローを表します。 

**ダイレクト ルーティングによる内部ユーザー (メディアは Office 365 内の Teams トランスポート リレーが中継)**

[![Microsoft Teams オンライン通話フロー 図 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*図 18 - ダイレクト ルーティングによる内部ユーザー (メディアは Office 365 内の Teams トランスポート リレーが中継)*

次の点に注意してください。
 
- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびメディア、およびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- 顧客ネットワーク内のクライアントから Office 365 へのシグナリングおよびメディアは、フロー 4 を使用します。


**ダイレクト ルーティングを使用するリモート ユーザー (メディアは Office 365 のメディア サーバー (MP) 経由でルーティング)**

[![Microsoft Teams オンライン通話フロー 図 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*図 19 - ダイレクト ルーティングを使用するリモート ユーザー (メディアは Office 365 のメディア サーバー (MP) 経由でルーティング)*
 
次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびメディア、およびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- インターネット上のクライアントから Office 365 へのシグナリングおよびメディアは、フロー 3 を使用します。

**内部ユーザーのダイレクト ルーティング (メディアはバイパス)**

[![Microsoft Teams オンライン通話フロー 図 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*図 20 - 内部ユーザーのダイレクト ルーティング (メディアはバイパス)*
 
次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- 顧客ネットワーク内のクライアントから Office 365 へのシグナリングは、フロー 4 を使用します。

- 顧客ネットワーク内のクライアントから顧客ネットワーク内の SBC へのメディアは、5B を使用します。

**ダイレクト ルーティングによるリモート ユーザー (メディアのパイパスは Office 365 内の Teams トランスポート リレーが中継)**

[![Microsoft Teams オンライン通話フロー 図 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*図 21 - ダイレクト ルーティングによるリモート ユーザー (メディアのパイパスは Office 365 内の Teams トランスポート リレーが中継)*

次の点に注意してください。

- SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- インターネット上のクライアントから Office 365 へのシグナリングは、フロー 3 を使用します。

- インターネット上のクライアントから顧客ネットワーク内の SBC へのメディアでは フロー 3 および 4 が使用され、Office 365 内の Teams トランスポート リレーにより中継されます。 

**リモート ユーザーのダイレクト ルーティング (メディアのバイパスはダイレクト)**

[![Microsoft Teams オンライン通話フロー 図 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*図 22 - リモート ユーザーのダイレクト ルーティング (メディアのバイパスはダイレクト)*
 
次の点に注意してください。

- SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- インターネット上のクライアントから Office 365 へのシグナリングは、フロー 3 を使用します。

- インターネット上のクライアントから顧客ネットワーク内の SBC へのメディアは、 フロー 2 を使用します。

**ダイレクト ルーティング (メディア バイパス) – PSTN ヘアピン コール (通話の転送を原因とする)**

[![Microsoft Teams オンライン通話フロー 図 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*図 23 - ダイレクト ルーティング (メディア バイパス) – PSTN ヘアピン コール (通話の転送を原因とする)*
 
次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- PSTN から PSTN への通話のヘアピンが発生すると、クライアントはシグナリングおよびメディア ループに含まれなくなります。

- 顧客ネットワーク内の SBC インスタンス A から顧客ネットワーク内の SBC インスタンス B までのメディア (A と B は同じインスタンスでも構いません) は、フロー 5C を使用します。

**ダイレクト ルーティング (メディアは Office 365 を経由) – 2 つのテナントの間での PSTN ヘアピン コール**

[![Microsoft Teams オンライン通話フロー 図 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*図 24 - ダイレクト ルーティング (メディアは Office 365 を経由) – 2 つのテナントの間での PSTN ヘアピン コール*
 
次の点に注意してください。

- SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。

- SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。

- PSTN から PSTN への通話のヘアピンが発生すると、クライアントはシグナリングおよびメディア ループに含まれなくなります。

- 顧客ネットワーク X 内の SBC インスタンス A からSBC インスタンス B へのメディアは、Office 365 メディア サーバー経由で中継される必要があり、バイパス モードは使用できません。

## <a name="teams-with-express-route-optimization"></a>Express Route による Teams の最適化

[![Microsoft Teams オンライン通話フロー 図 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*図 25 - Express Route による Teams の最適化*
 
Express Route が正当化されて展開されているケースでは、Teams のフローはフロー 4 からフロー 1 に、またフロー 4' からフロー 1' に再ルーティングできます。 ただし、Teams アプリケーションは、フロー 4 および 4' 経由のインターネット上の Office 365 フローに強く依存するため、これらのフローはブロックされない必要があります。 

Skype for Business のハイブリッド エッジ トラフィックは、外部ユーザーとの通信および他のテナントとのフェデレーションを行うために、Express Route ではなくインターネットにルーティングされることに注意してください。 

非対称のフローを防ぐには、再ルーティングは双方向に行う必要があります。 つまり、顧客ネットワーク内のアドレスは、(最適化のために) インターネットまたは Express Route のいずれを経由してもルーティング可能ですが、両方を経由することはできません。

次に例を示します。

**顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):**

[![Microsoft Teams オンライン通話フロー 図 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*図 26 - 顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継)*
 
**大まかな手順:**
1. 顧客ネットワーク内の Teams ユーザー A が、フロー 2 経由で URL ドメイン名 (DNS) を解決します。
2. 顧客ネットワーク内の Teams ユーザーが、フロー 1 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。
3. 顧客ネットワーク内の Teams ユーザーが、フロー 1 経由で "招待状" を ICE 候補と共に Office 365 に送信します。
4. Office 365 が、フロー 3 経由で Teams の外部ユーザーに通知を送信します。
5. Teams の外部ユーザーが、フロー 3 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。
6. Teams の外部ユーザーが、フロー 3 経由 "回答" を ICE 候補と共に送信し、これはフロー 1 経由で Teams ユーザー A に再び転送されます。
7. Teams ユーザー A および Teams ユーザー B が ICE 接続テストを実行してフロー 1 および フロー 3 を選択し、これらは Office 365 内の Teams トランスポート リレーにより中継されます。
8. Teams ユーザーが、フロー 1 およびフロー 3 経由でテレメトリを Office 365 に送信します。

>**注**: フロー 4 を要求する他のマイクロ サービスへの Teams の依存をサポートするために、フロー 4 を有効にする必要があります。
