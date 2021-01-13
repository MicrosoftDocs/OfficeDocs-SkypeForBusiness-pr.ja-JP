---
title: Skype for Business Server の簡易 URL の DNS 要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: Skype for Business Server の DNS レコードを実装する前に、このトピックの簡易 URL に関する考慮事項を確認してください。'
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834587"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Skype for Business Server の簡易 URL の DNS 要件

**概要:** Skype for Business Server の DNS レコードを実装する前に、このトピックの簡易 URL に関する考慮事項を確認してください。

簡単な URL を使用すると、ユーザーは会議に簡単に参加できます。また、管理者は Skype for Business Server 管理ツールに簡単にアクセスできます。 簡易 URL は独自のドメインを使用しますが、定義する SIP ドメインと一致しすることはできません。 

Skype for Business Server は、会議、ダイヤルイン、および管理者の 3 つの簡単な URL をサポートしています。会議とダイヤルインの簡易 URL を設定する必要があります。また、管理簡易 URL はオプションです。 簡易 URL をサポートする必要があるドメイン ネーム システム (DNS) レコードは、これらの簡易 URL の定義方法、および簡易 URL の障害復旧をサポートするかどうかによって異なっています。 

## <a name="simple-url-scope"></a>簡易 URL スコープ

簡易 URL には、グローバル スコープを適用できます。また、組織内の各セントラル サイトで別々の簡易 URL を指定することもできます。 簡単なグローバル URL と簡単なサイト URL の両方が指定されている場合は、簡単なサイト URL が優先されます。 

ほとんどの場合、簡単な URL はグローバル レベルでのみ設定することをお勧めします。そのため、ユーザーの簡易 URL をあるサイトから別のサイトに移動しても変更されません。 例外は、異なるサイトのダイヤルイン ユーザーに異なる電話番号を使用する必要がある組織です。 サイトで 1 つの簡易 URL (ダイヤルイン簡易 URL など) をサイト レベルの簡易 URL に設定する場合は、そのサイトの他の簡易 URL もサイト レベルに設定する必要があります。

トポロジ ビルダーでは、グローバルな簡易 URL を設定できます。 サイト レベルで簡単な URL を設定するには、次のコマンドレットSet-CsSimpleURLConfigurationします。

簡易 URL を定義するには、DNS 構成で A または AAAA レコードを設定する必要があります。

## <a name="simple-url-naming-and-validation-rules"></a>簡易 URL の名前付け規則と入力規則
<a name="BK_Valid"> </a>

トポロジ ビルダーと Skype for Business Server 管理シェル コマンドレットは、簡易 URL に対していくつかの検証ルールを適用します。 ユーザーは、簡単な会議 URL およびダイヤルイン URL の設定を要求されますが、簡単な管理 URL の設定はオプションです。 各 SIP ドメインは独立した簡単な会議 URL を持つ必要がありますが、簡単なダイヤルイン URL と簡単な会議 URL については組織全体で必要な数は 1 つだけです。

組織内の各簡易 URL は一意の名前を持つ必要があります。また、別の簡易 URL のプレフィックスにすることはできません (たとえば、会議の簡易 URL として SfB2015.contoso.com/Meet を設定し、ダイヤルイン簡易 URL として SfB2015.contoso.com/Meet/Dialin を設定することはできません)。 簡易 URL 名には、プールの FQDN を含め、ポート情報を含めすることはできません (たとえば https://FQDN:88/meet 、許可されません)。 簡易 URL は、すべてプレフィックス https:// で始まる必要があります。 

簡易 URL の名前には、英数字 (すなわち、a ～ z、A ～ Z、0 ～ 9) およびピリオド (.) 以外は使用できません。 他の文字を使用すると、簡易 URL が予想どおりに機能しない可能性があります。

## <a name="changing-simple-urls-after-deployment"></a>展開後の簡易 URL の変更
<a name="BK_Valid"> </a>

初回の展開後に簡易 URL を変更する場合は、その変更が簡易 URL の DNS レコードと証明書に及ぼす影響について認識しておく必要があります。 簡易 URL の基本部分が変わる場合は、DNS レコードと証明書も変更する必要があります。 たとえば、ベース URL を SfB2015.contoso.com から meet.contoso.com に変更する変更を行う場合、DNS レコードと証明書を変更して https://SfB2015.contoso.com/Meet https://meet.contoso.com meet.contoso.com。 簡易 URL を次の URL に変更した場合、SfB2015.contoso.comのベース URL は変わっていないので、DNS または証明書の変更は https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings 必要はありません。

ただし、簡単な URL 名を変更するたびに、各ディレクターとフロントエンド サーバーで **Enable-CsComputer** を実行して変更を登録する必要があります。

## <a name="naming-examples-for-simple-urls"></a>簡易 URL の名前付け例
<a name="BK_Valid"> </a>

簡易 URL の命名には、推奨される 3 つのオプションがあります。選択するオプションによって、簡易 URL をサポートする DNS A レコードと証明書の設定方法が影響を受けます。各オプションでは、組織内の SIP ドメインごとに簡単な会議 URL を 1 つ構成する必要があります。 

簡単なダイヤルインおよび管理 URL については、所有している SIP ドメインの数とは関係なく、組織全体で必要な数は、常に 1 つだけです。

オプション 1 では、簡易 URL ごとに、新しい SIP ドメイン名を作成します。

このオプションを使用する場合は、簡易 URL ごとに独立した DNS A レコードが必要であり、証明書で各簡単な会議 URL を指定する必要があります。

**簡易 URL 命名オプション 1**


| **簡易 URL** <br/> | **例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://meet.contoso.com、 https://meet.fabrikam.com など (組織内の SIP ドメインごとに 1 つ)  <br/> |
| ダイヤルイン  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 管理者  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

オプション 2 では、簡易 URL はドメイン名とドメイン名にSfB2015.contoso.com。 このため、必要な DNS A レコードは 1 つだけであり、この DNS A レコードで、簡易 URL の 3 つのタイプすべてを有効にします。 この DNS A レコードは、このSfB2015.contoso.com。 この場合も、組織内の他の SIP ドメインについては、独立した DNS A レコードが必要です。 

**簡易 URL 命名オプション 2**


| **簡易 URL** <br/> | **例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://SfB2015.contoso.com/Meet、 https://SfB2015.fabrikam.com/Meet など (組織内の SIP ドメインごとに 1 つ)  <br/> |
| ダイヤルイン  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 管理者  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

SIP ドメインの数が多く、これらのドメインに独立した簡単会議 URL を持たせて、これらの簡易 URL の DNS レコードと証明書の要件をできるだけ少なくする場合は、オプション 3 が最も便利です。 

**簡易 URL 命名オプション 3**


| **簡易 URL** <br/> | **例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| ダイヤルイン  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 管理者  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>簡易 URL の障害復旧オプション
<a name="BK_Valid"> </a>

フロントエンド プールを含むサイトが複数ある場合に、DNS プロバイダーが GeoDNS をサポートしている場合は、障害復旧をサポートするために簡易 URL の DNS レコードを設定して、1 つのフロントエンド プール全体がダウンしても簡易 URL 機能を続行できます。 この障害復旧機能は、会議とダイヤルインの簡易 URL をサポートします。

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

次に、(meet.contoso.com のような) 会議簡易 URL を 2 つの GeoDNS アドレスに解決する CNAME レコードを作成します。

> [!NOTE]
> ネットワークがヘアピン (組織内部からのトラフィックを含め、すべての簡易 URL トラフィックを外部リンク経由でルーティングすること) を使用している場合は、外部 GeoDNS アドレスを構成して、その外部アドレスのみに会議簡易 URL を解決できます。

この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。 

ダイヤルイン簡易 URL でも同じ構成をセットアップできます。 これを行うには、DNS レコードに代わり、前の例のような追加  `dialin` `meet` のレコードを作成します。 管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。

この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。 外部アクセスの場合は、HTTPS GET lyncdiscover を監視して確認します。<sipdomain> 2 つのプールの外部 Web FQDN またはロード バランサー IP アドレスへの要求が成功しました。 たとえば、以下の要求では、**ACCEPT** ヘッダーが含まれないようにし、**200 OK** を戻す必要があります。

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。 接続エラーが検出された場合、これらのプールの VIP はポート 80、443、4443 を閉じる必要があります。


