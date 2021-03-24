---
title: オンプレミス ユーザーのクラウド ボイスメール サービスを計画します|PBX Skype for Business Server 2019
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
description: この記事では、Microsoft Cloud ボイスメール サービスを実装するための利点、計画上の考慮事項、および要件について説明します。 クラウド ボイスメールの構成の詳細については、「クラウド ボイスメールの構成」を参照してください。
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110283"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する

## <a name="overview"></a>概要

この記事では、オンプレミスユーザーに対して Microsoft Cloud ボイスメール サービスを実装するための利点、計画上の考慮事項、および要件について説明します。 クラウド ボイスメールの構成の詳細については [、「Configure Cloud ボイスメール サービス」を参照してください](configure-cloud-voicemail.md)。

クラウド ボイスメールは、Exchange Server 2019 または Exchange Online にメールボックスを持つ Skype for Business 2019 音声ユーザーのボイス メッセージング機能を提供する際に、Exchange ユニファイド メッセージング (UM) の代用として使用されます。 クラウド ボイスメールは、オンプレミスユーザーとオンライン ユーザーの両方に次の利点があります。

- 音声の文字起こしを強化したボイスメール応答と入金機能

- Skype for Business Online または Outlook クライアントを使用したユーザーの Exchange メールボックス内のボイスメールへのアクセス

- Microsoft 365 管理センターを使用してボイスメール オプションを管理する機能

- オンプレミスまたはクラウドでの Exchange メールボックスのサポート

- Exchange Online ユニファイド メッセージングからの既存のユーザー案内応答の活用

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後、ユーザーは Skype for Business Online クライアントを介して Exchange メールボックスのボイスメールにアクセスできなくなりました。

機能の比較の詳細については [、「Plan for Skype for Business Server」および「Exchange Server」を参照してください](plan-um-migration.md)。

Skype for Business Server 2019 は、メールボックスが以前のバージョンの Exchange Server (2013、 2016) にあるユーザーに対して引き続き Exchange UM を使用します。  Exchange Server と Skype for Business Server のバージョンに基づいて使用されるボイスメール ソリューションを理解することが、Skype for Business Server 2019 または Exchange Server 2019 への移行を計画する重要な部分です。 移行と相互運用性の詳細については [、「Plan for Skype for Business Server」および「Exchange Server」を参照してください](plan-um-migration.md)。

クラウド ボイスメールを使用すると、次の理由で管理タスクが大幅に簡素化されます。

- Exchange UM の役割を構成する必要はありません。
- クラウド ボイスメールのセットアップ タスクの方が簡単です。
- ボイスメール機能の更新はクラウドで直接配信されます。そのため、ユーザーは常に累積的な更新プログラム (CUs) への依存が少ない最新の機能と更新プログラムにアクセスできます。
- オンプレミスメールボックスとオンライン Exchange メールボックスの両方に対して同じ一連のコントロールを使用できます。 これらのコントロールの詳細については、「電話システムボイスメール [のセットアップ」を参照してください](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。

次の図は、ハイブリッド展開でのクラウド ボイスメールを示しています。

![SfB クラウドボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

応答されていない呼び出しは、次のように処理されます。  

1. オンプレミスの Skype for Business 2019 に登録されているユーザーの場合、応答のない通話は、オンプレミスの Skype for Business Server からオンライン クラウド ボイスメール サービスに送信されます。
2. サービスは、ボイスメール (文字起こしを含む) を処理します。
3. その後、サービスは、メールボックスがオンプレミスかオンラインかを選択して、ユーザーの Exchange メールボックスにボイスメールを入金します。  
4. ユーザーは、Skype for Business または Outlook クライアントからボイスメールにアクセスできます。

## <a name="requirements"></a>要件

次の要件では、サポートされているトポロジに Skype for Business Server が既に展開済みである必要があります。  要件はシナリオによって異なります。

- Exchange UM online を既に使用している場合、Skype for Business 2019 にアップグレードする場合は、ホストされているボイスメール ポリシーを変更し、ホスティング プロバイダーが正しく設定されていることを確認する必要があります。 詳細については、「Configure [Cloud ボイスメール サービス」を参照してください](configure-cloud-voicemail.md)。

- オンプレミスで Exchange UM を使用している場合、または Exchange UM をオンラインとオンプレミスで使用しているユーザーが混在している場合は、ホストされているボイスメール ポリシーとホスティング プロバイダーの両方を変更する必要があります。  詳細については、「Configure [Cloud ボイスメール サービス」を参照してください](configure-cloud-voicemail.md)。

- クラウド ボイスメールの新しい構成については、「Configure Cloud ボイスメール サービス」で説明 [されている手順に従います](configure-cloud-voicemail.md)。

上記の要件に加えて、以下の要件を Microsoft Cloud ボイスメール サービスに接続するように構成する必要があります。

- ハイブリッド接続。 Skype for Business Server が既に展開済みで、オンプレミス ユーザーに対してクラウド ボイスメールを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。 これは、分割ドメイン構成と呼ばれる場合があります。

   詳細については、「Plan hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」および「Configure](plan-hybrid-connectivity.md) hybrid connectivity between Skype for Business Server and Office [365」](configure-hybrid-connectivity.md)を参照してください。

- オンプレミス ユーザーは、Skype for Business Server エンタープライズ VoIPおよびホストボイスメールに対して有効にする必要があります。

- 外部 Exchange Web サービス (EWS) URL と自動検出を設定する必要があります。または一部のクラウド ボイスメール機能が制限されます。

- オンプレミスの Exchange サーバーがある場合は、「メールボックス ユーザー用にクラウド ボイスメールをセットアップする」の手順を使用してクラウド [ボイスExchange Server設定します](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)。

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、ボイス メッセージングの継続的なサービスを確保するために、移行を慎重に計画する必要があります。 以下の点にご注意ください。

- Exchange Server 2019 では Exchange UM 機能が提供されなくなりました
- Skype for Business Server 2019 が Exchange Online UM と統合されなくなりました

次の表に、クラウド ボイスメールのバージョンの相互運用性とサポートされるトポロジを示します。これは、ユーザーが使用している可能性のある Skype for Business Server のバージョンと、Exchange メールボックスを提供する可能なバージョンを比較します。 Exchange Online または 2019 で Skype for Business 2019 を使用する場合は、クラウド ボイスExchange Server必要があります。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | クラウド ボイスメール | クラウド ボイスメール |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | 非サポート | クラウド ボイスメール |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | サポート対象外 | クラウド ボイスメール |

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は、クラウド ボイスメールにアップグレードする必要があります。
- Exchange Server 2019 にアップグレードし、以前のバージョンの Exchange Server UM for Skype for Business Server ボイス メッセージングを使用している場合は、メールボックスのアップグレード前に Skype for Business Server 2019 にアップグレードする必要があります。  それ以外の場合、ボイス メッセージング機能は失われます。
- Skype for Business Server 2019 にアップグレードし、Exchange Online UM を使用してボイスメール用に Skype for Business Server 2015 を構成している場合、アカウントが Skype for Business Server 2019 に移動すると、ユーザーのボイスメールは Exchange Online UM からクラウド ボイスメールに自動的に移行されます。 

移行の計画の詳細については、「Plan for Skype for Business Server」および「移行の [計画」をExchange Serverしてください](plan-um-migration.md)。