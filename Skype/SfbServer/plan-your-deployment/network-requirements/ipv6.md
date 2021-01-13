---
title: Skype for Business での IPv6 の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '概要: Skype for Business Server をインストールする前に IPv6 を実装します。'
ms.openlocfilehash: dbb9977d8d11b130387eca9e87213c2760226142
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825247"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Skype for Business での IPv6 の計画
 
**概要:** Skype for Business Server をインストールする前に IPv6 を実装します。
  
Skype for Business Server には、IP バージョン 6 (IPv6) アドレスのサポートと、IP バージョン 4 (IPv4) アドレスの継続的なサポートが含まれています。 

IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。 世界中でデバイスの数が増えているので、使用可能な IPv4 アドレスが使い切れなっています。この理由から、多くの新しいデバイスが IPv6 アドレスの使用に移行しています。 IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。 これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。 

典型的な IPv4 アドレスの例には 192.0.2.235 などがありますが、IPv6 アドレスでは 2001:0db8:85a3:0000:0000:8a2e:0370:7334 のようになります。 IPv6 アドレスを使用するデバイスの書式設定と機能を変更するには、Skype for Business Server のインストールでいくつかの展開と構成に関する考慮事項が必要です。 

このトピックには、以下のセクションが含まれます。
  
- [IP アドレスの種類の概要](ipv6.md#over)
    
- [IPv6 の技術要件](ipv6.md#tech)
    
- [IPv6 の移行と共存に関する考慮事項](ipv6.md#migration)
    
IPv6 アドレスを使用すると判断した場合は [、「Skype for Business](ip-address-types.md) で IP アドレスの種類を構成する」の記事を参照してください。
  
## <a name="overview-of-ip-address-types"></a>IP アドレスの種類の概要
<a name="over"> </a>

Skype for Business Server で IP アドレスを構成する場合は、3 つのオプションがあります。 Skype for Business Server を構成して、IP バージョン 4 (IPv4)、IP バージョン 6 (IPv6)、または両方の組み合わせ (デュアル スタックと呼ばれる) のみをサポートできます。 各構成には、いくつか考慮すべき問題があります。
  
- **IPv4 のみ** IPv6 が作成されたのは、世界で IPv4 アドレスが使い切っているためです。 最終的には、IPv6 は世界中で完全にサポートされますが、現時点では、企業が通信する必要がある多くの企業やデバイスは IPv6 をまだサポートしていません。また、一部の時間はサポートされない可能性があります。 IPv4 専用の構成を使用すると、Skype for Business Server の実装が既存のほとんどのデバイスと通信できます。
    
- **IPv6 のみ** 逆に、完全な IPv6 実装では、多くの既存のデバイスとの通信が除外されます。
    
- **デュアル スタック** デュアル スタックは、IPv4 アドレスと IPv6 アドレスの両方が有効になっているネットワークです。 ほとんどの場合、完全 IPv4 から完全 IPv6 への移行には数年かかるため、この構成は Skype for Business Server でサポートされています。
    
以下のセクションでは、Skype for Business Server のさまざまな機能に対するこれら 3 つの構成間の互換性の概要を説明します。
  
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

ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。 両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。
  
|**クライアント エンドポイント 1**|**クライアント エンドポイント 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |デュアル スタック  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |デュアル スタック  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>会議
<a name="conf"> </a>

会議には、音声ビデオ、アプリケーション共有、およびホワイトボードやファイル共有のようなデータコラボレーション アプリケーションが含まれます。
  
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

トラフィックが IPv6 インターフェイスを経由する場合、Skype for Business Server は公衆交換電話網 (PSTN) 通話のメディア バイパスをサポートしません。 メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。 
  
|**プライマリ インターフェイス 1**|**PSTN インターフェイス (仲介サーバー上)**|**PSTN ゲートウェイの設定**|
|:-----|:-----|:-----|
|IPv4  <br/> |デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |IPv6  <br/> |
   
1. プライマリ インターフェイスは、Skype for Business Server コンポーネントと通信するインターフェイスです。
  
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
|**フロントエンド プール: IPv4** <br/> |はい  <br/> |必要  <br/> |いいえ  <br/> |
|**フロントエンド プール: デュアル スタック** <br/> |はい  <br/> |必要  <br/> |いいえ  <br/> |
|**フロントエンド プール: IPv6** <br/> |いいえ  <br/> |いいえ  <br/> |はい\*  <br/> |
   
\* この組み合わせはラボ環境でのみ使用してください。
  
次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。
  
**エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス**

||**エッジ プール (外部エッジ): IPv4** <br/> |**エッジ プール (外部エッジ): デュアル スタック** <br/> |**エッジ プール (外部エッジ): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**エッジ プール (内部エッジ): IPv4** <br/> |はい  <br/> |必要  <br/> |いいえ  <br/> |
|**エッジ プール (内部エッジ): デュアル スタック** <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |
|**エッジ プール (内部エッジ): IPv6** <br/> |いいえ  <br/> |いいえ  <br/> |はい\*  <br/> |
   
\* この組み合わせはラボ環境でのみ使用してください。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 の高度なエンタープライズ VoIP のサポート
<a name="Ent_V"> </a>

通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。 IPv6 のみを使用するエンドポイントは、これらの機能を使用できません。
  
> [!NOTE]
> デュアル スタック展開では、Skype for Business Server クライアントが IPv6 を使用して Skype for Business Server に接続する場合でも、Skype for Business Server は E9-1-1 をサポートするために適切な IPv4 アドレスをマップするために最善の努力を行います。 
  
IPv6 アドレスを持つ場所情報サービスはサポートされていません。
  
Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6 に対するその他の Skype for Business Server 機能のサポート
<a name="Ent_V"> </a>

前述の機能とコンポーネントに加えて、Skype for Business Server は次の機能に対して IPv6 をサポートします。
  
- **常設チャット**
    
    常設チャット用に IPv6 を構成するには、トポロジ ビルダーを使用します。 常設チャットの構成の詳細については、「常設チャット サーバーの展開」のドキュメントを参照してください。
    
- **Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**
    
    IPv4 か IPv6 かにかかわらず、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 の技術要件
<a name="tech"> </a>

Skype for Business Server を IPv6 用に構成する予定の場合は、次の要件に注意してください。
  
- Skype for Business Server で IPv6 アドレスを使用するには、検出して IPv6 アドレスに解決する必要があるレコードのドメイン ネーム システム (DNS) レコードを作成する必要があります。 IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。 展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。 自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。 クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。 移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。
    
- 各 IPv6 アドレスにはスコープがあります。 IPv6 アドレス指定に使用できる 3 つのスコープは、IPv6 グローバル アドレス (パブリック IPv4 アドレスと同様)、IPv6 一意のローカル アドレス (プライベート IPv4 アドレス範囲と同様)、および IPv6 リンク ローカル アドレス (IPv4 用 Windows Server の自動プライベート IP アドレスに似ています) です。 プール内のすべてのサーバーには、同じスコープの IPv6 アドレスが必要です。 
    
> [!IMPORTANT]
> IPv6 は複雑なトピックであり、ネットワーク チームとインターネット プロバイダーと慎重に計画し、Windows Server レベルおよび Skype for Business Server レベルで割り当てるアドレスが期待通り動作する必要があります。 IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 の移行と共存に関する考慮事項
<a name="migration"> </a>

IP バージョン 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。 パイロットを目的として、Lync Server 2010 と Skype for Business Server のデュアル スタック共存をテストできます。 プールの IPv6 (デュアル スタック ネットワーク) を有効にする前に、特定の中央サイトのすべてのプールを Skype for Business Server にアップグレードすることをお勧めします。 IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。
  
次のシナリオは、移行と共存でサポートされます。
  
- Skype for Business Server、Lync Server 2013、および IPv4 モードの Lync Server 2010 プールは、デュアル スタック モードで Skype for Business Server と共に使用されます。
    
- IPv6 専用モードの Skype for Business Server プール (IPv6 専用プールがサイロ化されている場合)。
    
## <a name="see-also"></a>関連項目
<a name="migration"> </a>

[Skype for Business で IP アドレスの種類を構成する](ip-address-types.md)

[IP Version 6 のアドレス指定アーキテクチャ](https://tools.ietf.org/html/rfc4291)
  
[IPv6 グローバル ユニキャスト アドレス形式](https://tools.ietf.org/html/rfc3587)
  
[一意のローカル IPv6 ユニキャスト アドレス](https://tools.ietf.org/html/rfc4193)
