---
title: オンプレミスユーザー用にクラウドボイスメールサービスを計画する |PBX Skype for Business Server 2019
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
description: この記事では、Microsoft クラウドボイスメールサービスを実装するための利点、計画に関する考慮事項、および要件について説明します。 クラウドボイスメールの構成の詳細については、「Cloud 留守番電話を構成する」を参照してください。
ms.openlocfilehash: d95d3674eb9119be07e8b588ec3fe0e619fb5f1c
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359133"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>オンプレミスユーザー用にクラウドボイスメールサービスを計画する

## <a name="overview"></a>概要

この記事では、オンプレミスのユーザー用に Microsoft クラウドボイスメールサービスを実装するための利点、計画に関する考慮事項、および要件について説明します。 クラウドボイスメールの構成の詳細については、「 [クラウドボイスメールサービスを構成する](configure-cloud-voicemail.md)」を参照してください。

クラウドボイスメールは、exchange ユニファイドメッセージング (UM) の代わりに、Exchange Server 2019 または Exchange Online にメールボックスを持つ Skype for Business 2019 音声ユーザーの音声メッセージング機能を提供します。 クラウドボイスメールには、オンプレミスのユーザーとオンラインユーザーの両方に対して次のような利点があります。

- 音声による留守番電話の応答と取り込み機能の強化

- Skype for Business Online または Outlook クライアントを使用して、ユーザーの Exchange メールボックス内のボイスメールにアクセスする

- Microsoft 365 管理センターを使用してボイスメールオプションを管理する機能

- 社内またはクラウドでの Exchange メールボックスのサポート

- Exchange Online ユニファイドメッセージングからの既存のユーザー案内応答の活用

> [!Important]
> Skype for Business Online は2021年7月31日に廃止されます。これは、ユーザーが Skype for Business Online クライアントを介して Exchange メールボックス内のボイスメールにアクセスできなくなります。

機能の比較の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。

Skype for Business Server 2019 は、メールボックスが以前のバージョンの Exchange Server (2013, 2016) にあるユーザーに対して Exchange UM を引き続き使用します。  Exchange Server および Skype for Business Server のバージョンに基づいてどのボイスメールソリューションを使用するかを理解することは、Skype for Business Server 2019 または Exchange Server 2019 に移行するための計画において重要な部分です。 移行と相互運用性の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。

クラウドボイスメールを使用すると、管理タスクは以下の理由で大幅に簡素化されます。

- Exchange UM の役割を構成する必要はありません。
- クラウドボイスメールのセットアップタスクの方が簡単です。
- ボイスメール機能への更新はクラウドに直接配信されるため、ユーザーは常に最新の機能と更新プログラムにアクセスでき、累積的な更新プログラム (Cu) への依存度は低くなります。
- オンプレミスとオンラインの両方の Exchange メールボックスに対して同じコントロールセットがあります。 これらのコントロールの詳細については、「 [電話システムボイスメールをセットアップ](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)する」を参照してください。

次の図は、ハイブリッド展開でのクラウドボイスメールを示しています。

![SfB クラウドボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

応答のない通話は次のように処理されます。  

1. オンプレミスの Skype for Business 2019 に所属するユーザーは、オンプレミスの Skype for Business Server によってオンラインクラウドボイスメールサービスに送信されます。
2. サービスは、議事録を含めて、ボイスメールを処理します。
3. その後、メールボックスがオンプレミスかオンラインかにかかわらず、ユーザーの Exchange メールボックスにボイスメールがデポジットされます。  
4. ユーザーは、Skype for Business または Outlook クライアントから、ボイスメールにアクセスできます。

## <a name="requirements"></a>要件

次の要件は、サポートされているトポロジで Skype for Business Server を既に展開していることを前提としています。  要件は、シナリオによって異なります。

- 既に Exchange UM online を使用していて、Skype for Business 2019 にアップグレードする場合は、ホスト型ボイスメールポリシーを変更し、ホスティングプロバイダーが正しく設定されていることを確認する必要があります。 詳細については、「 [クラウドボイスメールサービスを構成する](configure-cloud-voicemail.md)」を参照してください。

- Exchange UM を社内で使用している場合、または Exchange UM online とオンプレミスを使用しているユーザーが混在している場合は、ホスト型ボイスメールポリシーとホスティングプロバイダーの両方を変更する必要があります。  詳細については、「 [クラウドボイスメールサービスを構成する](configure-cloud-voicemail.md)」を参照してください。

- クラウドボイスメールの新しい構成を行うには、「 [Configure Cloud ボイスメールサービス](configure-cloud-voicemail.md)」に記載されている手順に従ってください。

上記の要件に加えて、次の要件を構成して、Microsoft クラウドボイスメールサービスに接続する必要があります。

- ハイブリッド接続。 Skype for Business Server を既に展開しており、オンプレミスのユーザーに対してクラウドボイスメールを有効にする場合は、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。 これは、分割ドメイン構成と呼ばれることがあります。

   詳細については、「Skype for business [server と Microsoft 365 または office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md) する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。

- オンプレミスのユーザーは、Skype for Business Server のエンタープライズ Voip およびホストボイスメールに対して有効にする必要があります。

- 外部 Exchange Web サービス (EWS) の URL と自動検出を設定する必要があります。また、一部のクラウドボイスメール機能は制限されます。

- オンプレミスの Exchange サーバーがある場合は、「 [set Up Cloud ボイスメール For Exchange Server Mailbox Users](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)」の手順を使用してクラウドボイスメールをセットアップします。

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、ボイスメッセージングのサービスを継続するために、慎重に移行を計画する必要があります。 以下の点に注意します。

- Exchange Server 2019 が Exchange UM 機能を提供しなくなった
- Skype for Business Server 2019 が Exchange Online UM と統合されなくなりました

次の表は、クラウドボイスメールのバージョン相互運用性とサポートトポロジを示しています。これは、ユーザーが Exchange メールボックスを提供している可能性のあるバージョンで、ユーザーが所属している可能性のある Skype for Business Server バージョンを比較したものです。 Skype for Business 2019 を Exchange Online または Exchange Server 2019 で使用する場合は、クラウドボイスメールを使用する必要があります。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | クラウド ボイスメール | クラウド ボイスメール |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | クラウド ボイスメール | クラウド ボイスメール |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | サポート対象外 | クラウド ボイスメール |

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、exchange Server 2013 または2016で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は、クラウドボイスメールにアップグレードする必要があります。
- Exchange Server 2019 にアップグレードしていて、以前のバージョンの Exchange Server UM を Skype for Business Server voice messaging に対して使用している場合は、メールボックスをアップグレードする前に、Skype for Business Server 2019 にアップグレードすることをお勧めします。  それ以外の場合、音声メッセージング機能は失われます。
- Skype for Business Server 2019 にアップグレードするときに、Skype for Business Server 2015 が Exchange Online UM を使用してボイスメール用に構成されている場合、ユーザーのボイスメールは、アカウントが Skype for Business Server の2019に移動されるときに、Exchange Online UM からクラウドボイスメールに自動的に移行されます。 

移行の計画の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。
