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
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918693"
---
# <a name="plan-cloud-auto-attendants"></a>クラウド自動応答の計画

Exchange ユニファイド メッセージング (Exchange Server 2013 または Exchange Server 2016) で使用される自動応答は、Exchange Server 2019 または Exchange Online では使用できなくなりました。 Skype for Business Server 2019 の実装がこれらの Exchange バージョンのいずれかと統合されている場合は、電話システムに関連付けられているオンラインクラウド音声機能を使用する必要があります。 Exchange Server 2013 および 2016 にホームに Exchange UM サービスを移行する方法については [、「Plan for Skype for Business Server and Exchange Server](plan-um-migration.md) migration」を参照してください。

つまり、自動応答のようなユニファイド メッセージング機能を使用する場合は、Skype for Business Server 2019 のハイブリッド実装が必要になります。 詳細 [については、「Skype for Business Server と Microsoft 365 または Office 365](configure-hybrid-connectivity.md) の間のハイブリッド接続を構成する」を参照してください。

自動応答は、顧客の呼び出しを受け付けて案内応答を再生し、メニュー オプションを提供し、音声またはダイヤル パッドを使用して発信者と対話して、通話を適切な宛先にルーティングするクラウド サービスです。 各自動応答には、Microsoft Teams 管理センターの自動応答に直接リンクされるリソース アカウント *(「* リソース アカウントの構成」を [参照)](configure-onprem-ra.md)が Skype for Business Server 2019 システムに割り当てられます。 自動 [応答とは何か](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 、自動応答に関するオプションと機能の詳細については、「クラウド自動応答とは」を参照してください。

> [!NOTE]
> 複数の Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号を自動応答に割り当てできます。

クラウド自動応答への着信呼び出しは、次に示すように、いくつかのパスのいずれかを受け取る場合があります。

![自動応答の図](../../SfBServer2019/media/AA-plan-concept.png)

1. Skype for Business Server 2019 経由
2. セッション ボーダー[コントローラーとダイレクト](/MicrosoftTeams/direct-routing-border-controllers.md)[ルーティングを使用する](/MicrosoftTeams/direct-routing-plan.md)
3. Microsoft 365 または Microsoft 365 にOffice。

以下も参照してください。

- [クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)
- [着信呼び出しへの自動応答とルーティング](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>要件

次の要件は、サポートされているトポロジに Skype for Business Server 2019 が既に展開済みである必要があります。  要件はシナリオによって異なります。

- Exchange UM をオンラインまたはオンプレミスで既に使用している場合に、Skype for Business 2019 にアップグレードする場合は、自動応答の構造をキャプチャし、クラウドの自動応答を使用してクラウドに再作成する必要があります。 詳細については、「Exchange UM 自動応答または呼び出しキューを電話システムに移動 [する」を参照してください](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

- クラウド自動応答の新しい構成については、「リソース アカウントの構成」で説明されている  [手順に従います](configure-onprem-ra.md)。

上記の要件に加えて、Microsoft Cloud 自動応答サービスに接続するには、次の要件を構成する必要があります。

- ハイブリッド接続。 Skype for Business Server を既に展開済みで、オンプレミス ユーザーに対してクラウド自動応答を有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続が設定されている必要があります。 これは、分割ドメイン構成とも呼ばれる場合があります。

   詳細については [、「Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- 自動応答に電話番号を割り当てる場合は、Office [365 Enterprise E5 ライセンスが必要](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) です。
- 自動応答ごとにオンライン[リソース アカウント](/MicrosoftTeams/manage-resource-accounts.md)または[](configure-onprem-ra.md)オンプレミス リソース アカウントを作成し、電話番号とライセンスを割り当てる。 

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、自動応答の継続的なサポートを確保するために、移行を慎重に計画する必要があります。 以下の点にご注意ください:

- Exchange Server 2019 では Exchange UM 機能が提供されなくなりました
- Exchange ユニファイド メッセージングがサポート終了モード
- Skype for Business Server 2019 は Exchange Online UM と統合されなくなりました

クラウド自動応答は、Skype for Business Server 2019、2015、および 2013 を使用して構成できます。

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 の Exchange UM を使用できますが、Exchange Server 2019 を使用している場合はクラウド自動応答にアップグレードする必要があります。

- Exchange Server 2019 にアップグレードする場合に、以前のバージョンの Exchange Server UM for Skype for Business Server ボイス メッセージングを使用している場合は、メールボックスのアップグレードの前に Skype for Business Server 2019 にアップグレードしてください。  そうしないと、音声メッセージング機能が失われます。

移行の計画の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>以前に実装した Exchange UM 自動応答システムの移行

現在、Exchange 2013 または 2016 で作成された UM 自動応答システムのクラウドへの自動移行はサポートされていません。 自動応答システムを手動で再作成するには、次の操作を行う必要があります。

1. Exchange 管理 PowerShell コマンドを使用して、入れ子になった自動応答や通話キューなど、古い自動応答システムの構造を確認します。  
2. 各 UM 自動応答ノードに関連付けられた音声合成スクリプトまたは録音されたメッセージのコピーを作成します。
3. テスト用の電話番号とライセンスをオブジェクトに割り当てるなど、各自動応答ノードのオンプレミス エンドポイントを作成します。 これで、電話システムのようなオンライン サービスで使用されるオンプレミスの電話番号ライセンスを割り当てる機能が追加されました。
4. Microsoft Teams と電話システムを使用して、新しいクラウド自動応答サービスを実装します。 実装の [詳細については、「リソース アカウントを構成](configure-onprem-ra.md) する」を参照してください。 これを行う場合は、音声合成スクリプトまたは各 UM 自動応答ノードに関連付けられている録音されたメッセージをアップロードします。
5. クラウド自動応答の機能をテストします。
6. 古い Exchange UM 自動応答に割り当てられている電話番号を、新しく作成したメインクラウド自動応答に再割り当てします。

これらの [手順の詳細については、「Exchange UM 自動応答または通話キューを電話システム](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) に移動する」を参照してください。

ニーズを満たす構造と、顧客を効率的にガイドするスクリプトがある場合は、「リソース アカウントを構成する」に [進んでください](configure-onprem-ra.md)。

> [!CAUTION]
> [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)で説明したように、Server 2015 で作成された Exchange UM 自動応答を Server 2019 を実行しているサーバーに移動しないでください。 当分の間、共存モードで実行されている Skype for Business Server 2015 プールに保持する必要があります。

## <a name="see-also"></a>関連項目

[Skype for Business Server と Exchange Server の移行の計画](plan-um-migration.md)

[リソース アカウントの構成](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [着信呼び出しに自動的に応答してルーティングする](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)

[KB4480742: 連絡先オブジェクトを Skype for Business Server 2019 に移動した後、サブスクライバー アクセスまたは自動応答への呼び出しが高速ビジーおよび "500 Server Internal" エラーで失敗する](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
