---
title: オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する|PBX Skype for Business Server 2019
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
description: この記事では、Microsoft クラウド ボイスメール サービスを実装するための利点、計画に関する考慮事項、および要件について説明します。 クラウド ボイスメールの構成の詳細については、「クラウド ボイスメールの構成」を参照してください。
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662092"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する

## <a name="overview"></a>概要

この記事では、オンプレミス ユーザー向け Microsoft クラウド ボイスメール サービスを実装するための利点、計画に関する考慮事項、および要件について説明します。 クラウド ボイスメールの構成の詳細については、「クラウド ボイスメール サービス [の構成」を参照してください](configure-cloud-voicemail.md)。

クラウド ボイスメールは、Exchange Server 2019 または Exchange Online 上にメールボックスを持つ Skype for Business 2019 音声ユーザー向け音声メッセージング機能を提供する際に、Exchange ユニファイド メッセージング (UM) の代用です。 クラウド ボイスメールは、オンプレミスユーザーとオンライン ユーザーの両方に次の利点があります。

- 拡張音声トランスクリプションを使用したボイスメールの応答および入金機能

- Skype for Business Online または Outlook クライアントを使用してユーザーの Exchange メールボックスのボイスメールにアクセスする

- Microsoft 365 管理センターを使用してボイスメール オプションを管理する機能

- オンプレミスまたはクラウドでの Exchange メールボックスのサポート

- Exchange Online ユニファイド メッセージングからの既存のユーザー案内応答の活用

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後、ユーザーは Skype for Business Online クライアントを介して Exchange メールボックスのボイスメールにアクセスできなくなりました。

機能の比較の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)」を参照してください。

Skype for Business Server 2019 は、メールボックスが以前のバージョンの Exchange Server (2013、2016) にあるユーザーに対して引き続き Exchange UM を使用します。  skype for Business Server 2019 または Exchange Server 2019 への移行を計画する上で、Exchange Server および Skype for Business Server のバージョンに基づいて使用されるボイスメール ソリューションを理解することが重要です。 移行と相互運用性の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)」を参照してください。

クラウド ボイスメールを使用すると、次の理由から管理タスクが大幅に簡素化されます。

- Exchange UM の役割を構成する必要はありません。
- クラウド ボイスメールのセットアップ タスクは簡単です。
- ボイスメール機能の更新プログラムはクラウドに直接配信されます。そのため、ユーザーは常に、累積的な更新プログラム (CUs) への依存が少ない最新の機能と更新プログラムにアクセスできます。
- オンプレミスの Exchange メールボックスとオンライン Exchange メールボックスの両方に対して同じ一連のコントロールを使用できます。 これらのコントロールの詳細については、「電話システム ボイスメールのセットアップ [」を参照してください](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。

次の図は、ハイブリッド展開でのクラウド ボイスメールを示しています。

![SfB クラウド ボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

応答のない呼び出しは、次のように処理されます。  

1. オンプレミスの Skype for Business 2019 にホームしているユーザーの場合、応答のない通話はオンプレミスの Skype for Business Server からオンライン クラウド ボイスメール サービスに送信されます。
2. サービスは、トランスクリプションを含むボイスメールを処理します。
3. 次に、このサービスは、メールボックスがオンプレミスかオンラインかに関わりますが、ユーザーの Exchange メールボックスにボイスメールを保存します。  
4. ユーザーは、Skype for Business または Outlook クライアントからボイスメールにアクセスできます。

## <a name="requirements"></a>Requirements

次の要件は、サポートされているトポロジに Skype for Business Server が既に展開済みである必要があります。  要件はシナリオによって異なります。

- 既に Exchange UM をオンラインで使用している場合に Skype for Business 2019 にアップグレードする場合は、ホスト型ボイスメール ポリシーを変更し、ホスティング プロバイダーが正しく設定されていることを確認する必要があります。 詳細については、「クラウド ボイスメール サービス [の構成」を参照してください](configure-cloud-voicemail.md)。

- Exchange UM をオンプレミスで使用している場合、または Exchange UM をオンラインとオンプレミスで使用しているユーザーが混在している場合は、ホストボイスメール ポリシーとホスティング プロバイダーの両方を変更する必要があります。  詳細については、「クラウド ボイスメール サービス [の構成」を参照してください](configure-cloud-voicemail.md)。

- クラウド ボイスメールの新しい構成については、「クラウド ボイスメール サービスの構成」で説明 [されている手順に従います](configure-cloud-voicemail.md)。

上記の要件に加えて、Microsoft クラウド ボイスメール サービスに接続するように以下の要件を構成する必要があります。

- ハイブリッド接続。 Skype for Business Server を既に展開済みで、オンプレミス ユーザーに対してクラウド ボイスメールを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続が設定されている必要があります。 これは、分割ドメイン構成とも呼ばれる場合があります。

   詳細については [、「Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).

- オンプレミス のユーザーは、Skype for Business Server でエンタープライズ VoIPボイスメールに対して有効にする必要があります。

- 外部 Exchange Web サービス (EWS) の URL と自動検出を設定する必要があります。設定するか、クラウド ボイスメール機能の一部が制限されます。

- オンプレミスの Exchange サーバーがある場合は、「メールボックス ユーザー用にクラウド ボイスメールをセットアップする」の手順に従ってクラウド ボイス [メールExchange Server設定します](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)。

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、ボイス メッセージングの継続的なサービスを確保するために、移行を慎重に計画する必要があります。 以下の点にご注意ください:

- Exchange Server 2019 では Exchange UM 機能が提供されなくなりました
- Skype for Business Server 2019 は Exchange Online UM と統合されなくなりました

次の表に、クラウド ボイスメールのバージョンの相互運用性とサポートされるトポロジを示します。この表は、ユーザーがホームにしている可能性がある Skype for Business Server のバージョンと、Exchange メールボックスを提供する可能なバージョンを比較しています。 Exchange Online または Exchange Server 2019 で Skype for Business 2019 を使用する場合は、クラウド ボイスメールを使用する必要があります。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | クラウド ボイスメール | クラウド ボイスメール |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | サポートされていません | クラウド ボイスメール |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | サポート対象外 | クラウド ボイスメール |

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 の Exchange UM を使用できますが、Exchange Server 2019 を使用している場合はクラウド ボイスメールにアップグレードする必要があります。
- Exchange Server 2019 にアップグレードする場合に、以前のバージョンの Exchange Server UM for Skype for Business Server ボイス メッセージングを使用している場合は、メールボックスのアップグレードの前に Skype for Business Server 2019 にアップグレードしてください。  そうしないと、音声メッセージング機能が失われます。
- Skype for Business Server 2019 にアップグレードし、Skype for Business Server 2015 が Exchange Online UM のボイスメール用に構成されている場合、ユーザーのアカウントが Skype for Business Server 2019 に移動すると、ユーザーのボイスメールは Exchange Online UM からクラウド ボイスメールに自動的に移行されます。 

移行の計画の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)」を参照してください。
