---
title: ビジネス サーバー 2015 の Skype での簡単な Url の DNS の要件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: は、Skype のビジネス サーバー 2015 の DNS レコードを実装する前にこのトピックの簡単な URL の注意事項を確認します。'
ms.openlocfilehash: 87346a7c4c03837e5ebfdf0143cdb7c786f0e43b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での簡単な Url の DNS の要件
 
**の概要:**Skype のビジネス サーバー 2015 の DNS レコードを実装する前に、このトピックの簡単な URL の注意事項を確認します。
  
単純な Url、ユーザーの参加する会議を簡単、Skype の取得 Business Server 管理ツールを簡単に管理者にします。 単純な Url を定義する SIP ドメインのいずれにも一致する必要がありますが、自身のドメインを使用します。 
  
Skype ビジネス サーバーの次の 3 つの簡単な Url をサポートしています: ダイヤルして、管理者に対応対応し、ダイヤルインの簡単な Url を設定する必要があると、管理の簡単な URL は省略可能です。 単純な Url をサポートする必要があるドメイン ネーム システム (DNS) レコードは、このような単純な Url を定義する方法と、簡単な Url の災害復旧をサポートするかどうかによって異なります。 
  
## <a name="simple-url-scope"></a>単純な URL スコープ

グローバル スコープを持ち、単純な Url を構成することができます。 またはセントラル サイトごとに別の簡単な Url を指定するには、組織内。 グローバルの簡単な URL とサイトの簡単な URL の両方を指定すると、サイトの簡単な URL は優先順位を持ちます。 
  
ユーザーの対応の簡単な URL は変更されません 1 つのサイト間で移動するように、ほとんどの場合のみ、グローバル レベルで、簡単な Url を設定することを勧めします。 例外を別のサイトでは、ダイヤルイン ユーザーの別の電話番号を使用する必要がある組織となります。 サイト レベルの簡単な URL を使用するサイトで、ダイヤルの簡単な URL) などの 1 つの簡単な URL を設定する場合設定する必要も、他の単純な Url もサイト レベルにするには、そのサイトで注意してください。
  
トポロジ ビルダーでは、グローバルの簡単な Url を設定できます。 サイト レベルでの簡単な URL を設定するには、セット CsSimpleURLConfiguration コマンドレットを使用します。
  
簡単な URL を定義することも、A または AAAA レコードを DNS の構成の設定に必要です。
  
## <a name="simple-url-naming-and-validation-rules"></a>URL の簡単な名前付けと検証ルール
<a name="BK_Valid"> </a>

トポロジ ビルダーおよびビジネス サーバー管理シェル コマンドレットの Skype、簡単な Url のいくつかの入力規則を適用します。 即時会議およびダイヤルイン、単純な Url を設定する必要がありますが、オプションは、管理者のいずれかを設定します。 SIP ドメインごとに個別対応簡単な URL を持つ必要がありますが、組織全体の 1 つだけのダイヤルインの簡単な URL と 1 つの管理者の簡単な URL を必要します。
  
組織内のそれぞれの簡単な URL が一意の名前を持つ必要があり、別の簡単な URL のプレフィックスにすることはできません (たとえば、するを設定できませんでした、対応の簡単な URL として SfB2015.contoso.com/Meet と SfB2015.contoso.com/Meet/Dialin、ダイヤルインの簡単な URL として)。 簡単な URL の名前は、プールでは、いずれかまたはすべてのポート情報の FQDN を含めることはできません (たとえば、https://FQDN:88/meetは許可されていません)。 すべての単純な Url は、https:// の接頭辞で始まる必要があります。 
  
単純な Url は英数字のみを含めることができます (つまり、a-z、A-Z、0-9、およびピリオド (.)。 その他の文字を使用する場合、単純な Url 可能性がありますどおり動作します。
  
## <a name="changing-simple-urls-after-deployment"></a>配置後に簡単な Url を変更します。
<a name="BK_Valid"> </a>

最初の展開後に、簡単な URL を変更する場合は、変更に及ぼす影響について、DNS レコードと証明書の簡単な Url に注意してくださいする必要があります。 簡単な URL のベースが変更された場合は、DNS レコードと証明書もを変更する必要があります。 変更するたとえば、https://SfB2015.contoso.com/Meetをhttps://meet.contoso.comに変更を基本 URL SfB2015.contoso.com から meet.contoso.com、DNS レコードと meet.contoso.com を参照する証明書を変更する必要があります。簡単な URL を変更した場合はhttps://SfB2015.contoso.com/Meetにhttps://SfB2015.contoso.com/Meetings、SfB2015.contoso.com のベース URL は同じですがないため DNS、または証明書の変更が必要です。
  
簡単な URL 名を変更するたびに、変更を登録するには各ディレクターおよびフロント エンド サーバーで**有効にする CsComputer**を実行してください。
  
## <a name="naming-examples-for-simple-urls"></a>簡単な Url の名前付けの例
<a name="BK_Valid"> </a>

簡単な Url の名前を付けるための 3 つの推奨されるオプションがあります。 どのオプションを選択では、DNS の A レコードと単純な Url をサポートする証明書を設定する方法に影響を与えます。 各オプションでは、組織の SIP ドメインごとに 1 つの対応の簡単な URL を構成することにあります。 
  
ダイヤルの場合、組織全体である SIP ドメインの数に関係なく、管理者との 1 つ 1 つだけの簡単な URL を常に必要です。
  
オプション 1 では、簡単な URL ごとに、新しい SIP ドメイン名を作成します。
  
このオプションを使用する場合は、必要な個別の DNS A レコードごとの簡単な URL、および各対応の簡単な URL は、証明書の名前必要があります。
  
**簡単な URL 命名オプション 1**

|**簡易 URL** <br/> |**例** <br/> |
|:-----|:-----|
|会議  <br/> |https://meet.contoso.com、 https://meet.fabrikam.com、というように (組織内の SIP ドメインごとに 1 つ)  <br/> |
|ダイヤルイン  <br/> |https://dialin.contoso.com  <br/> |
|管理  <br/> |https://admin.contoso.com  <br/> |
   
オプション 2 では、単純な Url は、ドメイン名 SfB2015.contoso.com に基づいています。したがって、すべての 3 種類の簡単な Url を有効にする DNS A レコードを 1 つだけ必要があります。 この DNS の A レコードでは、SfB2015.contoso.com を参照します。さらに、する必要があります別の DNS の A レコードの他の SIP ドメインの組織で。 
  
**簡単な URL 命名オプション 2**

|**簡易 URL** <br/> |**例** <br/> |
|:-----|:-----|
|会議  <br/> |https://SfB2015.contoso.com/Meet、 https://SfB2015.fabrikam.com/Meet、というように (組織内の SIP ドメインごとに 1 つ)  <br/> |
|ダイヤルイン  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|管理  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
オプション 3 は、多くの SIP ドメインがあるし、する個別対応の簡単な Url があるが、これらの簡単な Url の DNS レコードと証明書の要件を最小限に抑えたい場合に適しています。 
  
**簡単な URL 命名オプション 3**

|**簡易 URL** <br/> |**例** <br/> |
|:-----|:-----|
|会議  <br/> |https://SfB2015.contoso.com/contosoSIPdomain/Meet  <br/> https://SfB2015.contoso.com/fabrikamSIPdomain/Meet  <br/> |
|ダイヤルイン  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|管理  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
## <a name="disaster-recovery-option-for-simple-urls"></a>簡単な Url の災害復旧オプション
<a name="BK_Valid"> </a>

フロント エンド プールが含まれているサイトが複数ある場合は、DNS プロバイダーは、GeoDNS をサポートしています、全体のフロント エンド プールを 1 つがダウンした場合でも、簡単な URL の機能が解決しないように災害復旧をサポートするための簡単な Url の DNS レコードを設定することができます。 この災害復旧の機能には対応し、簡単なダイヤルイン Url がサポートされています。
  
これを構成するには、2 つの GeoDNS アドレスを作成します。各アドレスは、障害の復旧目的でペアになった 2 つのプールに解決される、2 つの DNS A または CNAME レコードを持っています。1 つの GeoDNS アドレスは内部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または内部 Web FQDN に解決されます。もう 1 つの GeoDNS アドレスは外部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または外部 Web FQDN に解決されます。以下は、プールの FQDN を使用した、会議簡易 URL の例です。 
  
```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

次に、(meet.contoso.com のような) 会議簡易 URL を 2 つの GeoDNS アドレスに解決する CNAME レコードを作成します。
  
> [!NOTE]
> ネットワークでは、(を通じて、組織内から送信されるトラフィックを含め、外部リンクに、簡単な URL のすべてのトラフィックをルーティングする) hairpinning を使用する場合、だけ GeoDNS の外部アドレスを構成してのみに対応、簡単な URL を解決するには外部アドレスです。
  
この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。 
  
ダイヤルイン簡易 URL でも同じ構成をセットアップできます。 ような以前の例では、追加のレコードを作成するには、代わりに`dialin`の`meet`の DNS レコードです。 管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。
  
この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。 外部アクセスは、HTTPS を取得 lyncdiscover はそのことを確認するのにを監視します。<sipdomain> 外部 web FQDN またはロード バランサーの IP アドレスの 2 つのプールへの要求は、成功でした。 たとえば、次の要求の**ACCEPT**ヘッダーが含まれていない必要があります、返す必要があります**200 OK**。
  
```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。接続問題が検出された場合、これらのプールの VIP は、ポート 80、443、および 4443 を閉じる必要があります。
  

