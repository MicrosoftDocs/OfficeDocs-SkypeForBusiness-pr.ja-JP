---
title: Skype for Business Server の単純な Url の DNS 要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '概要: Skype for Business Server の DNS レコードを実装する前に、このトピックで簡単な URL の考慮事項を確認してください。'
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888476"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Skype for Business Server の単純な Url の DNS 要件

**概要:** Skype for Business Server の DNS レコードを実装する前に、このトピックの簡単な URL の考慮事項を確認してください。

簡単な Url を使用すると、ユーザーは簡単に会議に参加できるようになり、管理者にとって Skype for Business Server の管理ツールがさらに簡単になります。 単純な Url では独自のドメインが使用されます。これは、定義した SIP ドメインと一致しない必要があります。 

Skype for Business Server では、次の3つの簡単な Url (会議、ダイヤルイン、管理者) がサポートされています。会議とダイヤルインの簡単な url を設定する必要があります。管理者の単純な URL は省略可能です。 単純な Url をサポートするために必要なドメインネームシステム (DNS) レコードは、これらの単純な Url を定義した方法と、単純な Url の障害回復をサポートするかどうかによって異なります。 

## <a name="simple-url-scope"></a>単純な URL スコープ

グローバルなスコープを持つように単純な Url を構成することも、組織内のセントラルサイトごとに異なる簡単な Url を指定することもできます。 グローバルな単純 URL とサイトの単純 URL の両方が指定されている場合は、サイトの単純な url が優先されます。 

ほとんどの場合、単純な url の設定はグローバルレベルでのみ行うことをお勧めします。そのため、あるサイトから別のサイトに移動しても、ユーザーの単純な URL が変わらないようにすることをお勧めします。 例外として、さまざまなサイトのダイヤルインユーザーに異なる電話番号を使用する必要がある組織が挙げられます。 1つの単純な URL (ダイヤルインの単純な url など) をサイトレベルの単純な URL として設定する場合は、そのサイトの他の単純な Url もサイトレベルに設定する必要があることに注意してください。

トポロジビルダーでは、グローバルな単純 Url を設定することができます。 サイトレベルで単純な URL を設定するには、Set-CsSimpleURLConfiguration コマンドレットを使用します。

単純な URL を定義する場合も、DNS 構成で A/AAAA レコードを設定する必要があります。

## <a name="simple-url-naming-and-validation-rules"></a>単純な URL の名前付けと入力規則
<a name="BK_Valid"> </a>

トポロジビルダーと Skype for Business Server 管理シェルコマンドレットでは、単純な Url に対して複数の入力規則を適用します。 会議とダイヤルインのための単純な Url を設定する必要がありますが、管理者用の設定は省略可能です。 各 SIP ドメインは、個別の単純な url を持つ必要がありますが、組織全体に1つのダイヤルインの単純な url と管理者の単純な URL を1つだけ用意する必要があります。

組織内の各単純 URL には一意の名前を指定する必要があります。また、別の単純な URL のプレフィックスとして使用することはできません (たとえば、SfB2015.contoso.com/Meet の単純な url と SfB2015.contoso.com/Meet/Dialin をダイヤルインの単純な URL として設定することはできません)。 単純な URL 名には、任意のプールの FQDN または任意のポート情報を含めることhttps://FQDN:88/meetはできません (たとえば、許可されません)。 すべての単純な Url は、https://プレフィックスで始める必要があります。 

単純な Url には、英数字 (a ~ z、A ~ z、0-9、ピリオド (.) のみを含めることができます。 他の文字を使用している場合、単純な Url は期待どおりに動作しない可能性があります。

## <a name="changing-simple-urls-after-deployment"></a>展開後の単純な Url の変更
<a name="BK_Valid"> </a>

最初の展開後に単純な URL を変更する場合は、変更によって、単純な Url の DNS レコードと証明書にどのように影響するかに注意する必要があります。 単純な URL のベースが変更された場合は、DNS レコードと証明書も変更する必要があります。 たとえば、to https://SfB2015.contoso.com/Meet https://meet.contoso.comから MEET.CONTOSO.COM へのベース URL の変更は、SfB2015.contoso.com を参照するように DNS レコードと証明書を変更する必要があるためです。 Simple URL をからhttps://SfB2015.contoso.com/Meetにhttps://SfB2015.contoso.com/Meetings変更した場合、SfB2015.contoso.com のベース url は変わりません。そのため、DNS や証明書の変更は必要ありません。

ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの**有効化**] を実行して、変更を登録する必要があります。

## <a name="naming-examples-for-simple-urls"></a>単純な Url の名前付けの例
<a name="BK_Valid"> </a>

簡単な Url に名前を付けるための推奨される3つのオプションがあります。 どちらのオプションを選択するかは、DNS A レコードと単純な Url をサポートする証明書のセットアップ方法によって決まります。 各オプションで、組織内の各 SIP ドメインに対して、単一の会議の単純 URL を構成する必要があります。 

使用している SIP ドメインの数に関係なく、ダイヤルイン用の組織全体に、または管理者用に1つだけ簡単な URL を作成する必要があります。

オプション1では、各シンプル URL の新しい SIP ドメイン名を作成します。

このオプションを使用する場合は、各シンプル URL に個別の DNS A レコードが必要です。また、それぞれの [simple URL] を証明書で指定する必要があります。

**簡単な URL の名前付けオプション1**


| **単純な URL** <br/> | **例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| 即時  <br/>          | https://meet.contoso.com、 https://meet.fabrikam.comなどの場合 (組織の SIP ドメインごとに1つ)  <br/> |
| ダイヤルイン  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 同期  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

オプション2では、ドメイン名 SfB2015.contoso.com に基づいて単純な Url が作成されます。 そのため、3種類の単純な Url をすべて有効にする DNS A レコードは1つだけである必要があります。 この DNS A レコードは SfB2015.contoso.com を参照しています。 さらに、組織内の他の SIP ドメイン用の DNS A レコードも別途必要です。 

**簡単な URL の名前付けオプション2**


| **単純な URL** <br/> | **例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 即時  <br/>          | https://SfB2015.contoso.com/Meet、 https://SfB2015.fabrikam.com/Meetなどの場合 (組織の SIP ドメインごとに1つ)  <br/> |
| ダイヤルイン  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 同期  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

オプション3は、多数の SIP ドメインを持っていて、それらのユーザーが単純な Url を個別に指定して、DNS レコードと証明書の要件を最小限に抑える必要がある場合に最も役立ちます。 

**簡単な URL の名前付けオプション3**


| **単純な URL** <br/> | **例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| 即時  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| ダイヤルイン  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 同期  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>簡単な Url の障害回復オプション
<a name="BK_Valid"> </a>

フロントエンドプールが含まれている複数のサイトがあり、DNS プロバイダーが GeoDNS をサポートしている場合は、フロントエンドプール全体が停止した場合でも、簡単な URL 機能が続行されるように、単純な URL の DNS レコードを設定することができます。 この障害回復機能は、会議とダイヤルインのシンプルな Url をサポートしています。

これを構成するには、2つの GeoDNS アドレスを作成します。 各アドレスには2つの DNS A レコードまたは CNAME レコードがあり、これらは1つのプールに対応しているため、それらは共に災害回復目的でペアリングされます。 内部アクセスには1つの GeoDNS アドレスが使われ、2つのプールの内部 web FQDN またはロードバランサー IP アドレスに解決されます。 その他の GeoDNS アドレスは、外部アクセスに使われ、2つのプールの外部 web FQDN またはロードバランサー IP アドレスに解決されます。 次に示すのは、プールの Fqdn を使用した [simple URL の会議] の例です。 

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

次に、会議の単純な URL (meet.contoso.com など) を2つの GeoDNS アドレスに解決する CNAME レコードを作成します。

> [!NOTE]
> ネットワークで hairpinning (組織内から送信されるトラフィックを含む、すべての単純な URL トラフィックをルーティングする) が使用されている場合、外部 GeoDNS アドレスを構成して、それに合わせて単純な URL を解決することができます。外部住所。

この方法を使用する場合は、ラウンドロビン方式を使って要求を2つのプールに配布するか、主に1つのプール (地理的に近い場所にあるプールなど) に接続して、次の場合にのみ他のプールを使用するように、各 GeoDNS アドレスを構成できます。接続に失敗します。 

ダイヤルインの単純な URL に同じ構成を設定することができます。 これを行うには、前の例のように、DNS レコード`dialin`で`meet`の代用として、他のレコードを作成します。 管理者の簡易 URL については、このセクションで既に説明した3つのオプションのいずれかを使用します。

この構成が設定されたら、監視アプリケーションを使用して、エラーを監視するために HTTP 監視を設定する必要があります。 外部アクセスの場合、監視して HTTPS GET lyncdiscover があることを確認します。<sipdomain> 2つのプールの外部 web FQDN またはロードバランサー IP アドレスへの要求が成功します。 たとえば、次の要求には**ACCEPT**ヘッダーが含まれておらず、 **200 OK**を返す必要があります。

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

内部アクセスの場合は、2つのプールの内部 web FQDN またはロードバランサー IP アドレスのポート5061を監視する必要があります。 接続エラーが検出された場合、これらのプールの VIP は、ポート80、443、4443を閉じる必要があります。


