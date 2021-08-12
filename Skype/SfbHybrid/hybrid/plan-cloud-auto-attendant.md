---
title: クラウド自動応答を計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 2019 年にクラウド自動応答を使用するSkype for Business Server
ms.openlocfilehash: 0a9eaa3498541371314f268f2d4dfaef2200ab457267fe98f631430ce7c2f035
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315053"
---
# <a name="plan-cloud-auto-attendants"></a>クラウド自動応答の計画

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Exchange ユニファイド メッセージング (Exchange Server 2013 または Exchange Server 2016) で使用される自動応答は、Exchange Server 2019 または Exchange Online で使用できなくなりました。 Skype for Business Server 2019 の実装がこれらの Exchange バージョンのいずれかと統合されている場合は、電話システム に関連付けられているオンラインクラウド音声機能を使用する必要があります。 Exchange サーバー 2013 および 2016 にExchange UM サービスをクラウドに移行する方法については、「plan for Skype for Business Server and [Exchange Server](plan-um-migration.md) migration」を参照してください。

これは、自動応答のようなユニファイド メッセージング機能を使用する場合、Skype for Business Server 2019 のハイブリッド実装を持つという本質的な意味です。 詳細[については、「Configure hybrid connectivity between Skype for Business Serverと Microsoft 365またはOffice 365」](configure-hybrid-connectivity.md)を参照してください。

自動応答は、顧客の呼び出しを受け入れ、案内応答を再生し、メニュー オプションを提供し、音声またはダイヤル パッドを使用して発信者と対話して、通話を適切な宛先にルーティングするクラウド サービスです。 各自動応答には、Skype for Business Server 2019 システムのリソース アカウント *(「* リソース アカウントの構成」を [参照)](configure-onprem-ra.md)が割り当て、Microsoft Teams 管理センターの自動応答に直接リンクされます。 自動 [応答の詳細と](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 自動応答のオプションと機能の詳細については、「クラウド自動応答とは」を参照してください。

> [!NOTE]
> 自動応答には、複数の Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号を割り当てできます。

クラウド自動応答への着信呼び出しでは、次に示すように、いくつかのパスのいずれかを実行できます。

![自動応答の図](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. セッション ボーダー[コントローラーとダイレクト ルーティング](/MicrosoftTeams/direct-routing-border-controllers.md)[を使用する](/MicrosoftTeams/direct-routing-plan.md)
3. オンラインまたはオンラインのMicrosoft 365経由Office 365。

以下も参照してください。

- [クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)
- [着信呼び出しへの自動応答とルーティング](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>要件

次の要件では、サポートされているトポロジSkype for Business Server 2019 を既に展開していることを前提とします。  要件はシナリオによって異なります。

- Exchange UM をオンラインまたはオンプレミスで既に使用している場合、Skype for Business 2019 にアップグレードする場合は、自動応答の構造をキャプチャし、クラウド自動応答を使用してクラウドに再作成する必要があります。 詳細については、「UM 自動応答[または通話キュー Exchangeの移動」を参照電話システム。](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- クラウド自動応答の新しい構成については、「リソース アカウントの構成」で説明されている  [手順に従います](configure-onprem-ra.md)。

上記の要件に加えて、Microsoft Cloud 自動応答サービスに接続するように以下の要件を構成する必要があります。

- ハイブリッド接続。 Skype for Business Server が既に展開済みで、オンプレミス ユーザーに対してクラウド自動応答を有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。 これは、分割ドメイン構成と呼ばれる場合があります。

   詳細については、「Skype for Business Server と Microsoft 365 または Office 365 のハイブリッド接続を計画する」および[「Skype for Business Server](plan-hybrid-connectivity.md)と Microsoft 365 または Office 365 のハイブリッド接続を構成する」[を参照してください](configure-hybrid-connectivity.md)。

- 自動応答に電話番号を割り当てる場合は[、E5](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)ライセンスOffice 365 Enterprise必要があります。
- 自動応答ごとに[オンライン リソース アカウント](/MicrosoftTeams/manage-resource-accounts.md)または[](configure-onprem-ra.md)オンプレミス リソース アカウントを作成し、電話番号とライセンスを割り当てる。 

## <a name="migration-and-interoperability"></a>移行と相互運用性

2019 年または Skype for Business Server Exchange Server 2019 の展開を計画している場合は、自動応答の継続的なサポートを確保するために、移行を慎重に計画する必要があります。 以下の点にご注意ください:

- Exchange Server 2019 では、UM Exchange機能が提供されなくなりました
- Exchangeユニファイド メッセージングが終了モード
- Skype for Business Server 2019 が UM と統合Exchange Onlineなくなりました

クラウド自動応答は、2019 年Skype for Business Server 2015 年、2013 年に構成できます。

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は、クラウド自動応答にアップグレードする必要があります。

- Exchange Server 2019 にアップグレードし、Skype for Business Server ボイス メッセージング用に以前のバージョンの Exchange Server UM を使用している場合は、メールボックスのアップグレード前に Skype for Business Server 2019 にアップグレードをお勧めします。  それ以外の場合、ボイス メッセージング機能は失われます。

移行の計画の詳細については[、「Plan for Skype for Business Server」および「Exchange Server」を参照してください](plan-um-migration.md)。

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>以前に実装された UM 自動応答Exchange移行する

現時点では、2013 年または 2016 年に作成された UM 自動応答システムのクラウドへの自動移行Exchangeサポートされていません。 自動応答システムを手動で再作成するには、次の操作を行う必要があります。

1. 管理者Exchange PowerShell コマンドを使用して、入れ子になった自動応答や通話キューなど、古い自動応答システムの構造を確認します。  
2. 各 UM 自動応答ノードに関連付けられたテキスト読み上げスクリプトまたは記録されたメッセージのコピーを作成します。
3. テスト電話番号とライセンスをオブジェクトに割り当てるなど、自動応答ノードごとにオンプレミス エンドポイントを作成します。 オンライン サービスで使用されるオンプレミスの電話番号ライセンスを割り当てる機能が電話システム。
4. 新しいクラウド自動応答サービスを実装し、Microsoft Teamsと電話システム。 「実装 [の詳細については、リソース アカウントを](configure-onprem-ra.md) 構成する」を参照してください。 これを行う場合は、各 UM 自動応答ノードに関連付けられたテキスト読み上げスクリプトまたは記録されたメッセージをアップロードします。
5. クラウド自動応答の機能をテストします。
6. UM 自動応答に割り当てられた電話番号Exchange新しく作成されたメインクラウド自動応答に再割り当てします。

これらの[手順の詳細についてはExchange UM 自動](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)応答または通話キューの移動を参照電話システムを参照してください。

ニーズを満たす堅実な構造と、顧客を効率的に導くスクリプトがある場合は、「リソース アカウントの構成」に [進んでください](configure-onprem-ra.md)。

> [!CAUTION]
> [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)で説明したように、サーバー 2015 で作成Exchange UM 自動応答をサーバー 2019 を実行しているサーバーに移動しないでください。 当分の間、共存モードで実行されている 2015 Skype for Business Serverプールに保持する必要があります。

## <a name="see-also"></a>関連項目

[Skype for Business Server と Exchange Server の移行の計画](plan-um-migration.md)

[リソース アカウントの構成](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)

ExchangeUM:[着信呼び出しに自動的に応答してルーティングする](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[ハイブリッド接続を構成するには、Skype for Business ServerとMicrosoft 365またはOffice 365](configure-hybrid-connectivity.md)

[KB4480742: サブスクライバー アクセスまたは自動応答への呼び出しは、2019 年に連絡先オブジェクトを移動した後、高速ビジー状態で失敗し、"500 Server Internal" エラー Skype for Business Serverします。](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)