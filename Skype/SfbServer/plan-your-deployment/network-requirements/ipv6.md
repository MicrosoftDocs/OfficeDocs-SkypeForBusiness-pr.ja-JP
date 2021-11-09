---
title: IPv6 の計画を立Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '概要: IPv6 をインストールする前に実装Skype for Business Server。'
ms.openlocfilehash: 21fa37d187f32c9b679a49a3b8181b1a5e2732d1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849750"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>IPv6 の計画を立Skype for Business
 
**概要:** IPv6 をインストールする前に、IPv6 をSkype for Business Server。
  
Skype for Business Serverには、IP バージョン 6 (IPv6) アドレスのサポートと、IP バージョン 4 (IPv4) アドレスの継続的なサポートが含まれます。 

IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。 世界中のデバイスの数が増えているので、使用可能な IPv4 アドレスが使い切っています。この理由から、多くの新しいデバイスが IPv6 アドレスの使用に移行しています。 IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。 これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。 

典型的な IPv4 アドレスの例には 192.0.2.235 などがありますが、IPv6 アドレスでは 2001:0db8:85a3:0000:0000:8a2e:0370:7334 のようになります。 IPv6 アドレスを使用するデバイスの書式設定と機能の変更には、インストール時にいくつかの展開と構成Skype for Business Serverがあります。 

このトピックには、以下のセクションが含まれます。
  
- [IP アドレスの種類の概要](ipv6.md#over)
    
- [IPv6 の技術的要件](ipv6.md#tech)
    
- [IPv6 の移行と共存に関する考慮事項](ipv6.md#migration)
    
IPv6 アドレスを使用すると判断した場合は、「Ip アドレスの種類を構成する」の記事[Skype for Business](ip-address-types.md)してください。
  
## <a name="overview-of-ip-address-types"></a>IP アドレスの種類の概要
<a name="over"> </a>

IP アドレスを構成する場合は、次の 3 つのSkype for Business Server。 IP バージョン 4 (IPv4)、IP バージョン 6 (IPv6) のみ、または両方の組み合わせ (デュアル スタックと呼ばれる) のみをサポートするために、Skype for Business Server を構成できます。 各構成には、いくつか考慮すべき問題があります。
  
- **IPv4 のみ** 世界が IPv4 アドレスを使い切っているため、IPv6 が作成されました。 最終的には、IPv6 は世界中で完全にサポートされますが、現時点では、企業が通信する必要がある企業やデバイスの多くは、IPv6 をまだサポートしていません。また、一部の時間はサポートされない場合があります。 IPv4 専用の構成は、ユーザーの実装がSkype for Business Serverほとんどの既存のデバイスと通信するのに役立ちます。
    
- **IPv6 のみ** 逆に、完全な IPv6 実装では、多くの既存のデバイスとの通信が除外されます。
    
- **デュアル スタック** デュアル スタックは、IPv4 アドレスと IPv6 アドレスの両方が有効になっているネットワークです。 この構成は、Skype for Business Server IPv4 からフル IPv6 への移行には数年かかるため、サポートされています。
    
次のセクションでは、さまざまな機能に対するこれら 3 つの構成のSkype for Business Serverします。
  
> [!NOTE]
> クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。 
  
### <a name="client-registration"></a>クライアントの登録
<a name="client"> </a>

|**クライアント エンドポイント ネットワーク**|**サーバー ネットワーク**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |デュアル スタック  <br/> |
|デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |
|デュアル スタック  <br/> |IPv6  <br/> |
|IPv6  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>ピアツーピア クライアント
<a name="peer"> </a>

ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。
  
|**クライアント エンドポイント 1**|**クライアント エンドポイント 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |デュアル スタック  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>会議
<a name="conf"> </a>

会議には、音声/ビデオ、アプリケーション共有、ホワイトボードやファイル共有のようなデータコラボレーション アプリケーションが含まれます。
  
|**クライアント エンドポイント ネットワーク**|**サーバー ネットワーク**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |デュアル スタック  <br/> |
|デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |
|デュアル スタック  <br/> |IPv6  <br/> |
|IPv6  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>仲介サーバー/PSTN
<a name="med"> </a>

Skype for Business Serverが IPv6 インターフェイスを介している場合、公衆交換電話網 (PSTN) 通話のメディア バイパスはサポートされません。 メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。 
  
|**プライマリ インターフェイス 1**|**PSTN インターフェイス (仲介サーバー上)**|**PSTN ゲートウェイの設定**|
|:-----|:-----|:-----|
|IPv4  <br/> |デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |IPv6  <br/> |
   
1. プライマリ インターフェイスは、各コンポーネントと通信するSkype for Business Serverです。
  
### <a name="remote-user-peer-to-peer-communications"></a>リモート ユーザーのピアツーピア通信
<a name="remote"> </a>

リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。
  
|**リモート ユーザー ネットワーク**|**エッジ サーバー (外部エッジ)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>フロントエンド プールとエッジ プールの構成
<a name="FE_pool"> </a>

次の表に、フロント エンド サーバー プールと内部エッジ サーバー プールの間のサポート マトリックスを示します。
  
**フロントエンド プールとエッジ プール (内部エッジ) のマトリックス**

||**エッジ プール: IPv4** <br/> |**エッジ プール: デュアル スタック** <br/> |**エッジ プール: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**フロントエンド プール: IPv4** <br/> |はい  <br/> |はい  <br/> |不要  <br/> |
|**フロントエンド プール: デュアル スタック** <br/> |はい  <br/> |はい  <br/> |不要  <br/> |
|**フロントエンド プール: IPv6** <br/> |不要  <br/> |不要  <br/> |はい\*  <br/> |
   
\* この組み合わせは、ラボ環境でのみ使用します。
  
次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。
  
**エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス**

||**エッジ プール (外部エッジ): IPv4** <br/> |**エッジ プール (外部エッジ): デュアル スタック** <br/> |**エッジ プール (外部エッジ): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**エッジ プール (内部エッジ): IPv4** <br/> |はい  <br/> |はい  <br/> |不要  <br/> |
|**エッジ プール (内部エッジ): デュアル スタック** <br/> |不要  <br/> |はい  <br/> |不要  <br/> |
|**エッジ プール (内部エッジ): IPv6** <br/> |不要  <br/> |不要  <br/> |はい\*  <br/> |
   
\* この組み合わせは、ラボ環境でのみ使用します。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 の高度なエンタープライズ VoIP のサポート
<a name="Ent_V"> </a>

通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。 IPv6 のみを使用するエンドポイントでは、これらの機能を使用できません。
  
> [!NOTE]
> デュアルスタック展開では、Skype for Business Server クライアントが IPv6 を使用して Skype for Business Server に接続した場合でも、Skype for Business Server は E9-1-1 をサポートするために適切な IPv4 アドレスをマップするために最善の努力をします。 
  
IPv6 アドレスを含む位置情報サービスはサポートされていません。
  
Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6 Skype for Business Serverその他の機能サポート
<a name="Ent_V"> </a>

前述の機能とコンポーネントに加えて、Skype for Business Server IPv6 がサポートされています。
  
- **常設チャット**
    
    トポロジ ビルダーを使用して IPv6 for Persistent Chat を構成します。 常設チャットの構成の詳細については、「Deploying Persistent Chat Server」のドキュメントを参照してください。
    
- **Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**
    
    IPv4 か IPv6 かにかかわらず、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 の技術的要件
<a name="tech"> </a>

IPv6 用にSkype for Business Serverする場合は、次の要件に注意してください。
  
- IPv6 アドレスを Skype for Business Server で使用するには、IPv6 アドレスを検出して解決する必要があるレコードのドメイン ネーム システム (DNS) レコードを作成する必要があります。 IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。 展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。 自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。 クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。 移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。
    
- 各 IPv6 アドレスにはスコープがあります。 IPv6 アドレス指定に使用できる 3 つのスコープは、IPv6 グローバル アドレス (パブリック IPv4 アドレスと同様)、IPv6 一意のローカル アドレス (プライベート IPv4 アドレス範囲と同様)、IPv6 リンク ローカル アドレス (Windows Server for IPv4 の自動プライベート IP アドレスと同様) です。 プール内のすべてのサーバーには、同じスコープを持つ IPv6 アドレスが必要です。 
    
> [!IMPORTANT]
> IPv6 は複雑なトピックであり、Windows Server レベルおよび Skype for Business Server レベルで割り当てるアドレスが期待通り動作するために、ネットワーク チームとインターネット プロバイダーと慎重に計画する必要があります。 IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 の移行と共存に関する考慮事項
<a name="migration"> </a>

IP バージョン 6 (IPv6) は、Lync Server 2010 または Officeではサポートされていません。 パイロットの目的で、Lync Server 2010 とデュアル スタックSkype for Business Serverをテストできます。 プールの IPv6 (デュアルスタック ネットワーク) を有効にする前に、特定のセントラル サイトのすべてのプールを Skype for Business Server にアップグレードすることをお勧めします。 IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。
  
次のシナリオは、移行と共存でサポートされます。
  
- Skype for Business Server、Lync Server 2013、および Lync Server 2010 プールは IPv4 モードで、デュアル スタック モードで Skype for Business Serverと共に使用されます。
    
- Skype for Business Server IPv6 専用プールがサイロ化されている場合は、IPv6 専用モードでプールを使用します。
    
## <a name="see-also"></a>関連項目
<a name="migration"> </a>

[IP アドレスの種類を構成Skype for Business](ip-address-types.md)

[IP バージョン 6 アドレス指定アーキテクチャ](https://tools.ietf.org/html/rfc4291)
  
[IPv6 グローバル ユニキャスト アドレス形式](https://tools.ietf.org/html/rfc3587)
  
[一意のローカル IPv6 ユニキャスト アドレス](https://tools.ietf.org/html/rfc4193)
