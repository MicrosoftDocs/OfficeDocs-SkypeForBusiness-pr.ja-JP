---
title: Skype for Business での IPv6 の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802077"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Skype for Business での IPv6 の計画
 
**概要:** Skype for Business Server をインストールする前に IPv6 を実装します。
  
Skype for Business Server には、ip バージョン 6 (IPv6) アドレスのサポートと共に、IP バージョン 4 (IPv4) アドレスの引き続きサポートが含まれています。 

IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。 世界中で使用されているデバイスの数が増加しているため、利用可能な IPv4 アドレスが不足しています。このため、多くの新しいデバイスが IPv6 アドレスの使用に移行しています。 IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。 これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。 

典型的な IPv4 アドレスの例には 192.0.2.235 などがありますが、IPv6 アドレスでは 2001:0db8:85a3:0000:0000:8a2e:0370:7334 のようになります。 IPv6 アドレスを使うデバイスの書式設定と機能の変更には、Skype for Business Server のインストールで展開と構成の考慮事項がいくつか必要です。 

このトピックには次のセクションがあります。
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
IPv6 アドレスを使用する場合は、「 [Skype For business の IP アドレスの種類を構成する」](ip-address-types.md)を参照してください。
  
## <a name="overview-of-ip-address-types"></a>IP アドレス タイプの概要
<a name="over"> </a>

Skype for Business Server で IP アドレスを構成する際には、次の3つのオプションがあります。 Skype for Business Server では、IP バージョン 4 (IPv4)、IP バージョン 6 (IPv6)、またはその両方の組み合わせ (デュアルスタックとも呼ばれます) のみをサポートするように構成することができます。 各種の構成には、いくつか考慮すべき問題があります。
  
- **IPv4 のみ**IPv6 は IPv4 アドレスが不足しているために作成されました。 最終的には、IPv6 は世界中で完全にサポートされますが、現時点では、企業が通信する必要がある多くの会社やデバイスは IPv6 をサポートしていませんが、しばらくの間、そうでない可能性があります。 IPv4 のみの構成は、Skype for Business Server の実装が、既存のほとんどのデバイスと通信できるようにするために役立ちます。
    
- **IPv6 のみ**反対に、完全な IPv6 の実装では、多くの既存のデバイスとの通信が除外されます。
    
- **デュアルスタック**デュアルスタックは、IPv4 アドレスと IPv6 アドレスの両方が有効になっているネットワークです。 この構成は、Skype for Business Server でサポートされているため、ほとんどの場合、フル IPv4 からフル-IPv6 への移行は数年で完了します。
    
以下のセクションでは、Skype for Business Server のさまざまな機能について、これらの3つの構成間の互換性についての概要を示します。
  
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

会議には、音声ビデオ、アプリケーション共有、およびホワイト ボードやファイル共有などのデータ コラボレーション アプリケーションが含まれます。
  
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

Skype for Business Server では、トラフィックが IPv6 インターフェイスを通過している場合は、公衆交換電話網 (PSTN) 通話のメディアバイパスはサポートされません。 メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。 
  
|**プライマリインターフェイス1**|**PSTN インターフェイス (仲介サーバー上)**|**PSTN ゲートウェイの設定**|
|:-----|:-----|:-----|
|IPv4  <br/> |デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |IPv4  <br/> |
|デュアル スタック  <br/> |デュアル スタック  <br/> |IPv6  <br/> |
   
1. プライマリインターフェイスは、Skype for Business Server コンポーネントと通信するインターフェイスです。
  
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

次の表は、フロントエンドサーバープールと内部エッジサーバープールの間のサポートマトリックスを示しています。
  
**フロントエンド プールとエッジ プール (内部エッジ) のマトリックス**

||**エッジ プール: IPv4** <br/> |**エッジ プール: デュアル スタック** <br/> |**エッジ プール: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**フロントエンド プール: IPv4** <br/> |はい  <br/> |はい  <br/> |いいえ  <br/> |
|**フロントエンド プール: デュアル スタック** <br/> |はい  <br/> |はい  <br/> |いいえ  <br/> |
|**フロントエンド プール: IPv6** <br/> |なし  <br/> |いいえ  <br/> |はい\*  <br/> |
   
\*この組み合わせは、ラボ環境でのみ使用します。
  
次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。
  
**エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス**

||**エッジ プール (外部エッジ): IPv4** <br/> |**エッジ プール (外部エッジ): デュアル スタック** <br/> |**エッジ プール (外部エッジ): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**エッジ プール (内部エッジ): IPv4** <br/> |はい  <br/> |はい  <br/> |いいえ  <br/> |
|**エッジ プール (内部エッジ): デュアル スタック** <br/> |いいえ  <br/> |あり  <br/> |いいえ  <br/> |
|**エッジ プール (内部エッジ): IPv6** <br/> |いいえ  <br/> |いいえ  <br/> |はい\*  <br/> |
   
\*この組み合わせは、ラボ環境でのみ使用します。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 の高度なエンタープライズ VoIP のサポート
<a name="Ent_V"> </a>

通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。IPv6 だけを使用するエンドポイントは、これらのどの機能も使用できません。
  
> [!NOTE]
> デュアルスタック展開では、skype for business server クライアントが IPv6 を使用して Skype for business Server に接続している場合でも、E9-1 をサポートするために、適切な IPv4 アドレスをマッピングすることが最善の手段となります。 
  
IPv6 アドレスを使用した位置情報サービスはサポートされていません。
  
Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6 向けのその他の Skype for Business Server 機能のサポート
<a name="Ent_V"> </a>

前に説明した機能とコンポーネントに加えて、Skype for Business Server は次の機能について IPv6 をサポートしています。
  
- **常設チャット**
    
    "トポロジビルダー" を使用して、常設チャットの IPv6 を構成します。 常設チャットの設定の詳細については、「常設チャットサーバーのマニュアルの展開」を参照してください。
    
- **Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**
    
    IPv4 と IPv6 のいずれの場合でも、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 の技術要件
<a name="tech"> </a>

Skype for Business Server を IPv6 用に構成する場合は、次の要件を念頭に置いてください。
  
- Skype for Business Server で IPv6 アドレスを使用するには、IPv6 アドレスを検出し、解決する必要があるレコードに対して、ドメインネームシステム (DNS) レコードを作成する必要があります。 IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。 展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。 自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。
    
- 各 IPv6 アドレスにはスコープがあります。 IPv6 アドレス指定に使用できる3つのスコープは、IPv6 グローバルアドレス (パブリック IPv4 アドレスに似ています)、ipv6 固有のローカルアドレス (プライベート IPv4 アドレス範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP アドレスに似ています) です。Windows Server (IPv4 の場合)。 プール内のすべてのサーバーに、同じスコープの IPv6 アドレスが含まれている必要があります。 
    
> [!IMPORTANT]
> IPv6 は複雑なトピックであり、お客様のネットワークチームとお使いのインターネットプロバイダとの慎重な計画が必要となり、Windows Server レベルと Skype for Business Server レベルで割り当てたアドレスが期待どおりに動作することが保証されます。 IPv6 のアドレス指定と計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 の移行および共存の検討事項
<a name="migration"> </a>

IP version 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。 パイロット目的で、Lync Server 2010 および Skype for Business Server のデュアルスタック共存テストを行うことができます。 いずれかのプールで IPv6 (デュアルスタックネットワーク) を有効にする前に、特定のセントラルサイトのすべてのプールを Skype for Business Server にアップグレードすることをお勧めします。 IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。
  
次のシナリオは、移行と共存でサポートされます。
  
- Skype for Business Server、Lync Server 2013、および Lync Server 2010 プールは IPv4 モードで、デュアルスタックモードでの Skype for Business Server との共存ができます。
    
- Ipv6 専用プールが孤立している場合は、IPv6 専用モードの Skype for Business サーバープール。
    
## <a name="see-also"></a>関連項目
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[IP バージョン6アドレス体系](https://tools.ietf.org/html/rfc4291)
  
[IPv6 グローバルユニキャストアドレス形式](https://tools.ietf.org/html/rfc3587)
  
[一意のローカル IPv6 ユニキャストアドレス](https://tools.ietf.org/html/rfc4193)
