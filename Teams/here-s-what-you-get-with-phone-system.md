---
title: 電話システムで利用できる機能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'ビジネス向けの Microsoft 電話システムの計画とセットアップ方法について説明します。 '
ms.openlocfilehash: fa7acbd4593b44805b2f9044602f3521baacaaaf
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638346"
---
# <a name="heres-what-you-get-with-phone-system"></a>電話システムで利用できる機能

この記事では、電話システムの機能について説明します。 PBX (構内交換機) 交換として電話システムを使用する方法、および公衆交換電話網 (PSTN) に接続するためのオプションの詳細については、「[電話システムとは](what-is-phone-system-in-office-365.md)」を参照してください。

クライアントは PC、Mac、モバイルで利用できます。これは、タブレットや携帯電話から Pc やデスクトップの IP 電話へのデバイスの機能を提供します。 詳細については、「 [Microsoft Teams のクライアントを取得する](get-clients.md)」を参照してください。

  
## <a name="phone-system-features"></a>電話システムの機能

電話システムには、次の機能が用意されています。 特に記載がない限り、機能は Teams と Skype for Business Online の両方で利用できます。
  
|||
|:-----|:-----|
|**電話システムの機能** <br/> |**説明** <br/> |
|[クラウド自動応答](what-are-phone-system-auto-attendants.md) <br/> |外部および内部の発信者が組織内の会社のユーザーや部署に通話を配置して、通話を転送できるようにするメニューシステムを作成することができます。  <br/> |
|[クラウド通話キュー](create-a-phone-system-call-queue.md) <br/> |組織での通話キューの管理方法を構成することができます。たとえば、応答メッセージや音楽を保留にしたり、通話を処理する次の通話エージェントを検索したりできます。  <br/> |
|保留音 | 公衆交換電話網 (PSTN) からの外部通話が保留になっているときに、サービスによって定義された既定の音楽を再生します。 この機能は、通話キューへの通話に加えて、1対1の PSTN 同士の通話に対応しています。 この機能は、他のプラットフォームとの保留通知のパリティを提供します。 この機能は管理者が構成できますが、[現在は PowerShell 経由でのみ](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)設定できます。 PSTN 通話の提案転送でも、音楽を保留することはサポートされていません。|
|Answer/initiate (名前と電話番号)  <br/> |ユーザーがタッチして着信通話に応答し、完全な電話番号にダイヤルするか、またはクライアントで名前をクリックして発信通話を発信できるようにします。  <br/> |
|[着信の転送オプションと同時呼び出し](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |通話がどこにいても通話できるように転送ルールを設定したり、通話を同僚やボイスメールに転送したりすることができます。  <br/> |
|[グループ通話のピックアップとグループへの転送](call-sharing-and-group-call-pickup.md) <br/> | ユーザーが着信した通話を同僚と共有できるようにすることで、ユーザーが使用できない間に発生した通話に同僚が応答できるようにします。 ユーザーは着信の共有通話の通知方法を構成できるため、他の形式の通話共有 (着信の転送、同時呼び出しなど) よりも、受信者に対する影響が少なくなります。 |
|[通話と提案転送を転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |ユーザーが通話を他のユーザーに転送できるようにします。 または、自分のオフィスから離れて、会話を続ける必要がある場合は、自分の PC または IP 電話から携帯電話に通話を転送することができます。  <br/> |
|[ボイスメールへの着信転送](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | 通話中にユーザがボイスメールに転送することができます。 |
|[コール パークおよび取得](call-park-and-retrieve.md)  <br/> | ユーザーは、クラウドの Teams サービスで通話を保留にすることができます。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。 <br/> |
|検索から電話番号に発信  <br/> | [ダイヤル] コマンドを使用して名前または番号を指定することで、ユーザーが検索ボックスから通話を発信できるようにします。 <br/> |
|[発信者番号](how-can-caller-id-be-used-in-your-organization.md)  <br/> |社内からの通話には、会社のディレクトリから情報を取得する詳細な発信者番号が表示され、電話番号だけではなく、写真の ID と役職が表示されます。 外部電話番号からの通話の場合、電話サービスプロバイダによって提供される発信者番号認識が表示されます。 外部電話番号が企業ディレクトリ内のセカンダリ番号の場合は、企業ディレクトリからの情報が表示されます。  <br/> |
|デバイス切り替え  <br/> |ユーザーは、チームに接続されている別の HID デバイスで通話または会議を再生することができます。たとえば、PC スピーカーからヘッドセットに切り替えます。   <br/> |
|プレゼンスベースの通話ルーティング <br/> |プレゼンスを使って着信通信を制御します。ユーザーは、明示的に指定されたものを除き、すべての着信をブロックすることができます。  <br/> |
|[統合ダイヤルパッド](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | ユーザーは、名前または検索バーとダイヤルパッドの任意の場所で番号をダイヤルして、通話の発信プロセスを高速化することができます。 <br/> |
|フェデレーション通話  <br/> |フェデレーションされたテナント内のユーザーと安全に接続、通信、共同作業を行うことができます。  <br/> |
|[ビデオ通話の発信と受信](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | ユーザのアカウントがビデオ通話に対応している場合、ユーザはコンタクトと対面のビデオ通話を行うことができます。 必要なのは、カメラ、コンピュータのスピーカー、マイクだけです。 内蔵のオーディオデバイスがコンピューターに搭載されていない場合、ユーザーはヘッドセットを使用することもできます。<br/> |
|[クラウドボイスメール](set-up-phone-system-voicemail.md) <br/> | ユーザーがボイスメールを受信すると、ボイスメールが添付ファイルとしてメールとして送信されます。 ユーザーは、認定されたデスクトップ電話で、すべてのチームまたは Skype for business アプリケーションでメッセージを聞くことができます。 ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。   <br/> |
|[クラウドボイスメールのユーザー設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | ユーザーは、不在時の応答を含め、ボイスメール応答メッセージ、通話応答ルール、およびグリーティングの言語のクライアント設定を構成できます。   |
|[セカンダリ着信](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | PC に複数のスピーカーデバイスが接続されているユーザーは、既定のスピーカーに加えて、2台目のデバイスの着信音を設定することができます。 たとえば、PC と机のスピーカーに接続されているヘッドセットを使用しているユーザーは、着信があったときにヘッドセットと机スピーカーのどちらの輪を持っているかを選択して、通話を逃すことはありません。  |
|[ディスティンクティブリング通知](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)(Teams のみ)<br/> |通話の種類を区別できるように、通常の通話、着信の転送、委任された通話に対して、着信音を個別に選ぶことができます。  <br/> |
|[回線共有機能](shared-line-appearance.md) <br/> | 他のユーザーが自分の代わりに通話を発信および受信できるように、ユーザーが電話回線を共有できるようにします。|
|[取り込み中 (Teams](teams-calling-policy.md)のみ) <br/> | ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に、着信通話の処理方法を構成できる通話ポリシー。 通話先が電話に入っているときは、発信者は取り込み中の信号を受け取ります。 呼び出し元は不在着信通知を取得しますが、着信呼び出しに応答することはできません。 この機能は既定では無効になっていますが、テナント管理者が有効にすることができます。 |
|[通話ブロック](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | ユーザーが (PSTN) 電話番号をブロックされたリストに追加して、その番号からの次の着信がブロックされるのを防ぐことができます。|
|[一般的なエリア電話](set-up-common-area-phones.md) <br/> | 通常、一般的なエリアの電話は、ロビーや電話会議室など、複数のユーザーが利用できる領域に配置されています。 一般的なエリア携帯電話は、ユーザーではなくデバイスとして設定されるため、ネットワークに自動的にサインインすることができます。|
|[メディアバイパスのサポート](direct-routing-plan-media-bypass.md)(Teams で直接ルーティングのみ) <br/> | パフォーマンスを向上させるために、メディアは、Microsoft 電話システム経由で送信するのではなく、セッション境界コントローラー (SBC) とクライアントの間で保持されます。 |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC 高および DoD クラウドでの可用性
<a name="bkmk_setup"> </a>

以下の機能は、GCC 高および DoD クラウドでまだご利用いただけません。 
- [第2の着信音、ボイスメール、強化された委任の通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [ボイスメールへの着信転送](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 検索バーから電話番号に発信
- 保留音
- Azure AD 逆引き数値参照

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)
- [Microsoft Teams での Cloud Voice](cloud-voice-landing-page.md)
- [電話システムをセットアップする](setting-up-your-phone-system.md)
- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [電話システムのダイレクト ルーティング](direct-routing-landing-page.md)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Microsoft Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話システムの価格](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [通話と会議で仮想化されたデスクトップインフラストラクチャのチーム](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 
