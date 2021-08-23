---
title: オンプレミス クラウド ボイスメールのサービスを計画します|PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: この記事では、サービスを実装するための利点、計画上の考慮事項、および要件Microsoft クラウド ボイスメール説明します。 構成方法の詳細については、「クラウド ボイスメール構成」を参照クラウド ボイスメール。
ms.openlocfilehash: 7a2fea02417a271e3858adff435a2406fda8c5ae
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407166"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>オンプレミス ユーザークラウド ボイスメールサービスを計画する

## <a name="overview"></a>概要

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

この記事では、オンプレミス ユーザーに対して Microsoft クラウド ボイスメール サービスを実装するための利点、計画の考慮事項、および要件について説明します。 構成の詳細については、「configure クラウド ボイスメール[サービス」をクラウド ボイスメールしてください](configure-cloud-voicemail.md)。

クラウド ボイスメール は、Exchange ユニファイド メッセージング (UM) の代用として、Skype for Business 2019 または Exchange Server または Exchange Online にメールボックスを持つ Skype for Business 音声ユーザーにボイス メッセージング機能を提供します。 クラウド ボイスメール、オンプレミスユーザーとオンライン ユーザーの両方に次の利点があります。

- 音声の文字起こしを強化したボイスメール応答と入金機能

- ユーザーのメールボックス内のボイスメールへのアクセスExchangeオンライン クライアントまたはクライアントSkype for Business使用Outlookします。

- ボイスメール オプションを管理するためにMicrosoft 365 管理センターを使用する機能

- オンプレミスまたはクラウドExchangeメールボックスのサポート

- ユニファイド メッセージングからの既存のユーザー案内応答Exchange Online活用する

> [!Important]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その後、ユーザーは Exchange Online クライアントを介して Exchange Skype for Business メールボックスのボイスメールにアクセスできなくなりました。

機能の比較の詳細については[、「Plan for Skype for Business Server移行」をExchange Serverしてください](plan-um-migration.md)。

Skype for Business Server 2019 では、メールボックスが以前のバージョンの Exchange Server (2013、 2016) にあるユーザーに対して引き続き Exchange UM を使用します。  Exchange Server および Skype for Business Server バージョンに基づいて使用されるボイスメール ソリューションを理解することが、Skype for Business Server 2019 または Exchange Server 2019 への移行を計画する上で重要Exchange Serverです。 移行と相互運用性の詳細については[、「Plan for Skype for Business Server移行」Exchange Server参照してください](plan-um-migration.md)。

このクラウド ボイスメール、管理タスクは次の理由で大幅に簡素化されます。

- UM の役割を構成するExchangeはありません。
- アプリケーションのセットアップ タスククラウド ボイスメール簡単です。
- ボイスメール機能の更新はクラウドで直接配信されます。そのため、ユーザーは常に累積的な更新プログラム (CUs) への依存が少ない最新の機能と更新プログラムにアクセスできます。
- オンプレミスメールボックスとオンライン メールボックスの両方に対して同じExchangeがあります。 これらのコントロールの詳細については、「ボイスメールの[セットアップ」を電話システムしてください](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。

次の図は、ハイブリッド展開クラウド ボイスメールを示しています。

![SfB クラウド ボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

応答されていない呼び出しは、次のように処理されます。  

1. オンプレミスの Skype for Business 2019 にホームされたユーザーの場合、応答のない通話は、オンプレミスの Skype for Business Server によってオンライン クラウド ボイスメール サービスに送信されます。
2. サービスは、ボイスメール (文字起こしを含む) を処理します。
3. その後、サービスは、メールボックスがオンプレミスかオンラインExchange、ユーザーのメールボックスにボイスメールを入金します。  
4. ユーザーは、自分のボイスメールに自分のSkype for BusinessまたはOutlookできます。

## <a name="requirements"></a>要件

次の要件では、サポートされているトポロジSkype for Business Server既に展開済みである必要があります。  要件はシナリオによって異なります。

- Exchange UM オンラインを既に使用している場合、Skype for Business 2019 にアップグレードする場合は、ホストされているボイスメール ポリシーを変更し、ホスティング プロバイダーが正しく設定されていることを確認する必要があります。 詳細については、「Configure[クラウド ボイスメール サービス」を参照してください](configure-cloud-voicemail.md)。

- オンプレミスで Exchange UM を使用している場合、または Exchange UM をオンラインとオンプレミスで使用しているユーザーが混在している場合は、ホストされているボイスメール ポリシーとホスティング プロバイダーの両方を変更する必要があります。  詳細については、「Configure[クラウド ボイスメール サービス」を参照してください](configure-cloud-voicemail.md)。

- サービスの新しい構成については、「クラウド ボイスメール サービスの構成」で説明されている手順[クラウド ボイスメールします](configure-cloud-voicemail.md)。

上記の要件に加えて、以下の要件を構成して、サービスに接続Microsoft クラウド ボイスメールがあります。

- ハイブリッド接続。 Skype for Business Server が既に展開済みで、オンプレミス ユーザーに対して クラウド ボイスメール を有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。 これは、分割ドメイン構成と呼ばれる場合があります。

   詳細については、「plan [hybrid connectivity](plan-hybrid-connectivity.md) between Skype for Business Server and Microsoft 365 or Office 365」および「Configure [hybrid connectivity](configure-hybrid-connectivity.md)between Skype for Business Server and Office 365」 を参照してください。

- オンプレミス のユーザーは、ユーザーのアカウントとホストエンタープライズ VoIPに対して有効にするSkype for Business Server。

- 外部 Web Exchange Web サービス (EWS) URL と自動検出を設定するか、一部の機能クラウド ボイスメール制限する必要があります。

- オンプレミスのサーバーがある場合は、「Exchange メールボックス ユーザークラウド ボイスメールセットアップ」の手順に従ってクラウド ボイスメールを[Exchange Serverします](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)。

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype for Business Server 2019 および/または Exchange Server 2019 の展開を計画している場合は、ボイス メッセージングの継続的なサービスを確保するために、移行を慎重に計画する必要があります。 以下の点にご注意ください。

- Exchange Server 2019 では、UM Exchange機能が提供されなくなりました
- Skype for Business Server 2019 が UM と統合Exchange Onlineなくなりました

クラウド ボイスメール のバージョンの相互運用性とサポートされるトポロジを次の表に示します。これは、ユーザーが使用する可能性のある Skype for Business Server バージョンと、Exchange メールボックスを提供する可能なバージョンを比較します。 2019 年 2019 年クラウド ボイスメール 2019 年または 2019 年Skype for Businessを使用する場合は、Exchange OnlineをExchange Serverがあります。

| Skype/Lync のバージョン | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange ServerUM | Exchange ServerUM | クラウド ボイスメール | クラウド ボイスメール |
| Skype for Business Server 2015 | Exchange ServerUM | Exchange ServerUM | 非サポート | クラウド ボイスメール |
| Lync Server 2013 <br>  | Exchange ServerUM | Exchange ServerUM | サポート対象外 | クラウド ボイスメール |

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は クラウド ボイスメール にアップグレードする必要があります。
- Exchange Server 2019 にアップグレードし、Skype for Business Server ボイス メッセージング用に以前のバージョンの Exchange Server UM を使用している場合は、メールボックスのアップグレード前に Skype for Business Server 2019 にアップグレードをお勧めします。  それ以外の場合、ボイス メッセージング機能は失われます。
- Skype for Business Server 2019 にアップグレードし、Skype for Business Server 2015 が Exchange Online UM のボイスメール用に構成されている場合、ユーザーのボイスメールは、アカウントが Skype for Business Server 2019 に移動すると、Exchange Online UM から クラウド ボイスメール に自動的に移行されます。 

移行の計画の詳細については[、「Plan for Skype for Business Server」および「Exchange Server」を参照してください](plan-um-migration.md)。