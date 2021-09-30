---
title: Skype for Business Server の単純な URL の DNS 要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: Skype for Business Server の DNS レコードを実装する前に、このトピックの単純な URL に関する考慮事項を確認してください。'
ms.openlocfilehash: cbc8a6f99704f9c450847d0ca3c5173b0066715e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011721"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Skype for Business Server の単純な URL の DNS 要件

**概要:** Skype for Business Server の DNS レコードを実装する前に、このトピックの単純な URL に関する考慮事項を確認してください。

単純な URL を使用すると、ユーザーが会議に参加しやすくなり、管理者が Skype for Business Server 管理ツールを簡単に利用できます。 単純な URL は独自のドメインを使用します。これは、定義した SIP ドメインと一致する必要があります。 

Skype for Business Server では、会議、ダイヤルイン、管理者の 3 つの単純な URL がサポートされています。Meet と Dial-In の単純な URL を設定する必要があります。管理者の簡易 URL は省略可能です。 単純な URL をサポートするために必要なドメイン ネーム システム (DNS) レコードは、これらの単純な URL の定義方法、および簡易 URL の障害復旧をサポートするかどうかによって異なっています。 

## <a name="simple-url-scope"></a>単純な URL スコープ

簡易 URL には、グローバル スコープを適用できます。また、組織内の各セントラル サイトで別々の簡易 URL を指定することもできます。 簡単なグローバル URL と簡単なサイト URL の両方が指定されている場合は、簡単なサイト URL が優先されます。 

ほとんどの場合、単純な URL はグローバル レベルでのみ設定することをお勧めします。そのため、ユーザーがサイト間を移動してもユーザーの簡易 URL を満たしても変更されません。 ただし、異なるサイトのダイヤルイン ユーザーに異なる電話番号を使用する必要がある組織は例外です。 サイトで 1 つの単純な URL (ダイヤルイン簡易 URL など) をサイト レベルの単純な URL に設定する場合は、そのサイトの他の単純な URL もサイト レベルに設定する必要があります。

トポロジ ビルダーでグローバル簡易 URL を設定できます。 サイト レベルで簡単な URL を設定するには、次のコマンドレットSet-CsSimpleURLConfigurationします。

単純な URL を定義するには、DNS 構成で A レコードまたは AAAA レコードを設定する必要があります。

## <a name="simple-url-naming-and-validation-rules"></a>単純な URL の名前付けと検証ルール
<a name="BK_Valid"> </a>

トポロジ ビルダーと Skype for Business Server Management Shell コマンドレットは、単純な URL に対していくつかの検証ルールを適用します。 ユーザーは、簡単な会議 URL およびダイヤルイン URL の設定を要求されますが、簡単な管理 URL の設定はオプションです。 各 SIP ドメインは独立した簡単な会議 URL を持つ必要がありますが、簡単なダイヤルイン URL と簡単な会議 URL については組織全体で必要な数は 1 つだけです。

組織内の各単純な URL には一意の名前を付け、別の単純な URL のプレフィックスにすることはできません (たとえば、Meet 単純な URL として、 `SfB2015.contoso.com/Meet` および Dialin 単純な URL として設定することはできません `SfB2015.contoso.com/Meet/Dialin` )。 単純な URL 名には、プールの FQDN を含め、ポート情報を含めすることはできません (たとえば、 https://FQDN:88/meet 許可されません)。 簡易 URL は、すべてプレフィックス https:// で始まる必要があります。 

簡易 URL の名前には、英数字 (すなわち、a ～ z、A ～ Z、0 ～ 9) およびピリオド (.) 以外は使用できません。 他の文字を使用すると、簡易 URL が予想どおりに機能しない可能性があります。

## <a name="changing-simple-urls-after-deployment"></a>展開後の簡易 URL の変更
<a name="BK_Valid"> </a>

初回の展開後に簡易 URL を変更する場合は、その変更が簡易 URL の DNS レコードと証明書に及ぼす影響について認識しておく必要があります。 簡易 URL の基本部分が変わる場合は、DNS レコードと証明書も変更する必要があります。 たとえば、ベース URL を変更する場合は、参照する DNS レコードと証明書を変更 `https://SfB2015.contoso.com/Meet` `https://meet.contoso.com` `SfB2015.contoso.com` `meet.contoso.com` する必要があります `meet.contoso.com` 。 単純な URL をからに変更した場合、ベース URL は同じままなので、DNS や証明書の変更 `https://SfB2015.contoso.com/Meet` `https://SfB2015.contoso.com/Meetings` `SfB2015.contoso.com` は不要です。

ただし、単純な URL 名を変更するたびに、各ディレクターとフロントエンド サーバーで **Enable-CsComputer** を実行して変更を登録する必要があります。

## <a name="naming-examples-for-simple-urls"></a>簡易 URL の名前付け例
<a name="BK_Valid"> </a>

簡易 URL の命名には、推奨される 3 つのオプションがあります。選択するオプションによって、簡易 URL をサポートする DNS A レコードと証明書の設定方法が影響を受けます。各オプションでは、組織内の SIP ドメインごとに簡単な会議 URL を 1 つ構成する必要があります。 

簡単なダイヤルインおよび管理 URL については、所有している SIP ドメインの数とは関係なく、組織全体で必要な数は、常に 1 つだけです。

オプション 1 では、簡易 URL ごとに、新しい SIP ドメイン名を作成します。

このオプションを使用する場合は、簡易 URL ごとに独立した DNS A レコードが必要であり、証明書で各簡単な会議 URL を指定する必要があります。

**簡易 URL 命名オプション 1**


| **簡易 URL** <br/> | **例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://meet.contoso.com`、 `https://meet.fabrikam.com` など (組織内の SIP ドメインごとに 1 つ)  <br/> |
| ダイヤルイン  <br/>       | `<https://dialin.contoso.com>`  <br/>                                                                                  |
| 管理者  <br/>         | `<https://admin.contoso.com>`  <br/>                                                                                   |

オプション 2 では、単純な URL はドメイン名に基づいて作成されます `SfB2015.contoso.com` 。 このため、必要な DNS A レコードは 1 つだけであり、この DNS A レコードで、簡易 URL の 3 つのタイプすべてを有効にします。 この DNS A レコード参照 `SfB2015.contoso.com` 。 この場合も、組織内の他の SIP ドメインについては、独立した DNS A レコードが必要です。 

**簡易 URL 命名オプション 2**


| **簡易 URL** <br/> | **例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://SfB2015.contoso.com/Meet`、 `https://SfB2015.fabrikam.com/Meet` など (組織内の SIP ドメインごとに 1 つ)  <br/> |
| ダイヤルイン  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                                          |
| 管理者  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                                           |

SIP ドメインの数が多く、これらのドメインに独立した簡単会議 URL を持たせて、これらの簡易 URL の DNS レコードと証明書の要件をできるだけ少なくする場合は、オプション 3 が最も便利です。 

**簡易 URL 命名オプション 3**


| **簡易 URL** <br/> | **例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `<https://SfB2015.contoso.com/contosoSIPdomain/Meet>`  <br/> `<https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>`  <br/> |
| ダイヤルイン  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                            |
| 管理者  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>単純な URL の障害復旧オプション
<a name="BK_Valid"> </a>

フロントエンド プールを含むサイトが複数ある場合、DNS プロバイダーが GeoDNS をサポートしている場合は、障害復旧をサポートする簡易 URL の DNS レコードをセットアップして、フロントエンド プール全体がダウンしても単純な URL 機能が続行されます。 この障害復旧機能は、Meet と Dial-In の単純な URL をサポートします。

これを構成するには、2 つの GeoDNS アドレスを作成します。各アドレスは、障害の復旧目的でペアになった 2 つのプールに解決される、2 つの DNS A または CNAME レコードを持っています。1 つの GeoDNS アドレスは内部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または内部 Web FQDN に解決されます。もう一つの GeoDNS アドレスは外部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または外部 Web FQDN に解決されます。以下は、プールの FQDN を使用した、会議簡易 URL の例です。 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

次に、2 つの GeoDNS アドレスに対する Meet 単純な URL (など) を解決する `meet.contoso.com` CNAME レコードを作成します。

> [!NOTE]
> ネットワークがヘアピン (組織内部からのトラフィックを含め、すべての簡易 URL トラフィックを外部リンク経由でルーティングすること) を使用している場合は、外部 GeoDNS アドレスを構成して、その外部アドレスのみに会議簡易 URL を解決できます。

この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。 

ダイヤルイン簡易 URL でも同じ構成をセットアップできます。 これを行うには、前の例のような追加のレコードを  `dialin` 作成し、DNS レコードの代 `meet` わりに作成します。 管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。

この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。 外部アクセスの場合は、HTTPS GET lyncdiscover を監視して確認します。<sipdomain> 2 つのプールの外部 Web FQDN またはロード バランサー IP アドレスへの要求が成功しました。 たとえば、以下の要求では、**ACCEPT** ヘッダーが含まれないようにし、**200 OK** を戻す必要があります。

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。 接続エラーが検出された場合、これらのプールの VIP はポート 80、443、4443 を閉じる必要があります。


