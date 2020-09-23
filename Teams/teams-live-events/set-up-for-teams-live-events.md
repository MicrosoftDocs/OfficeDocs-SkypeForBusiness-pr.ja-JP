---
title: Microsoft Teams でのライブ イベントのセットアップ
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Teams でイベントのライブをセットアップします。セットアップの一環として、ネットワークの設定、ライセンスの割り当て、ライブ イベント機能とスケジュールの有効化、ビデオ配信ソリューションの設定も行います。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0e2d35152ae8a840a6e0c0943144380e7169fe8b
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203940"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Microsoft Teams でのライブ イベントのセットアップ

ライブ イベントをセットアップする際は、複数の手順を行う必要があります。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>手順 1: Teams でのライブ イベント用にネットワークを設定する

Teams で作成したライブ イベントを配信するには、[Teams 用に組織のネットワークを準備する](https://docs.microsoft.com/microsoftteams/prepare-network)必要があります。  

## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる

[ライブ イベントの作成とスケジュールを許可するユーザー](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events)と[ライブ イベントの視聴を許可するユーザー](plan-for-teams-live-events.md#who-can-watch-live-events)のそれぞれに適切なライセンスを割り当てるようにします。

## <a name="step-3-set-up-live-events-policies"></a>手順 3: ライブ イベント ポリシーを設定する

ライブ イベント ポリシーを使用して、ライブ イベントの主催が許可される組織内のユーザーと、それらのユーザーが作成するイベントで有効にする機能を制御します。 既定のポリシーを使用することも、1 つ以上のカスタム ライブ イベント ポリシーを作成することもできます。 カスタム ポリシーを作成したら、それを組織内のユーザーまたはユーザーのグループに割り当てます。

> [!NOTE]
> カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル (組織全体の既定) ポリシーが適用されます。 グローバル ポリシーの既定では、Teams ユーザーにはライブ イベントのスケジュールが有効にされ、ライブ キャプションと字幕 (文字起こし) は無効にされます。また、組織内のすべてのユーザーがライブ イベントに参加でき、録画設定は [常に録画] に設定されます。

### <a name="create-or-edit-a-live-events-policy"></a>ライブ イベント ポリシーを作成または編集する

<a name="bkcreatepolicy"> </a>

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**ライブイベントポリシー**]に移動します。
2. 次のいずれかの操作を行います。

    - 既存の既定のポリシーを編集する場合は、**[グローバル (組織全体の既定値)]** を選択します。
    - 新しいカスタム ポリシーを作成する場合は、[**追加**]を選択します。
    - カスタム ポリシーを編集する場合は、対象のポリシーを選択してから **[編集]** を選択します。

    組織のニーズに応じて変更できる設定は次のとおりです。

    ![ライブ イベント ポリシーの設定を示すスクリーン ショット](../media/teams-live-events-policies.png "Microsoft Teams 管理センターのライブ イベント ポリシーの設定を示すスクリーン ショット")

|Setting  |説明  |
|---------|---------|
|**タイトル**     |これはライブ イベント ポリシーのページに表示されるポリシーのタイトルです。 64 文字を超えるタイトルは使用できません。また、タイトルに特殊文字を含めることはできません。          |
|**説明**    |この設定を使用して、ポリシーのわかりやすい説明を追加します。         |
|**スケジュールを許可**     |この設定をオンにすると、組織内のユーザーが Teams でライブ イベントを作成し、スケジュールできるようになります。 ユーザーが外部アプリまたはデバイスで作成されたライブ イベントをスケジュールできるようにする場合は、追加の手順を行う必要がある点にご注意ください。 詳細については、「[ユーザーが外部アプリまたはデバイスで作成されたイベントをスケジュールできるようにする](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)」を参照してください。     |
|**出席者の議事録作成を許可する** |この設定は、Teams で作成されるイベントにのみ適用できます。 この設定をオンにすると、出席者にイベントのライブ キャプションと字幕を表示できます。         |
|**スケジュールされたライブ イベントに参加できるユーザー**    |次のいずれかのオプションを選びます。<br><br>**すべてのユーザー**: 組織外部のユーザーを含め、すべてのユーザーが出席できるライブ イベントを作成できます。 この設定では、ユーザーがライブ イベントをスケジュールするときに、Teams で **[パブリック]** タイプのアクセス許可が有効になります。<br> **組織内のすべてのユーザー**: 組織に追加された[ゲスト ユーザー](../add-guests.md)を含め、組織内のすべてのユーザーが出席できるライブ イベントを作成できます。 匿名ユーザーが出席するライブ イベントを作成することはできません。 この設定では、ユーザーがライブ イベントをスケジュールするときに、Teams で **[組織全体]** タイプのアクセス許可が有効になります。<br> **特定のユーザーまたはグループ**: 組織内の特定のユーザーまたはグループだけが出席できるライブ イベントを作成できます。 組織内のすべてのユーザーや匿名ユーザーが出席するライブ イベントを作成することはできません。 この設定では、ユーザーがライブ イベントをスケジュールするときに、Teams で **[ユーザーとグループ]** タイプのアクセス許可が有効になります。       |
|**録画設定**  <br>     | この設定は、Teams で作成されるイベントにのみ適用できます。 次のいずれかのオプションを選びます。 <br><br> **常に録画**: ユーザーが作成したライブ イベントは常に録画されます。 イベントの終了後、イベントのチーム メンバーは録画をダウンロードできます。また、出席者はイベントを視聴できます。 <br> **録画しない**: ユーザーが作成したライブ イベントは録画されません。 <br>**開催者が録画可能または不可**: ライブ イベントを録画するかどうかをユーザーが決定できます。 録画する場合は、イベントの終了後、イベントのチーム メンバーは録画をダウンロードできます。また、出席者はイベントを視聴できます。      

ライブ イベント ポリシーを設定するには、Windows PowerShell を使用することもできます。 詳細については、「[PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する](set-teams-live-events-policies-using-powershell.md)」を参照してください。 

### <a name="assign-a-live-events-policy-to-users"></a>ユーザーにライブ イベント ポリシーを割り当てる

カスタム ライブ イベント ポリシーを作成した場合、そのポリシーをユーザーに割り当てるとポリシーが有効になります。 <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>ユーザーが外部アプリまたはデバイスで作成されたイベントをスケジュールできるようにする

ユーザーが外部アプリまたはデバイスで作成されたイベントをスケジュールできるようにするには、次の手順も行う必要があります。

1. 組織内のユーザーに対して Microsoft Stream を有効にします。 Stream は、対象となる Microsoft 365 または Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして使用できます。 Stream は Business Essentials プランや Business Premium プランには含まれません。 詳細については、「[Microsoft Stream ライセンスの概要](https://docs.microsoft.com/stream/license-overview)」を参照してください。

>[!Note]
> [会議の記録用](../tmr-meeting-recording-change.md)に Microsoft Stream を使用して OneDrive for Business と SharePoint を使用するように変更した場合は、段階的なアプローチとなります。 起動時には、この機能を有効にすることができます。11月2021以降、Stream の使用を継続する場合は、すべてのユーザーが OneDrive for Business と SharePoint を使用して新しい会議のレコーディングを使用する必要があります。

      Learn more about how you can [assign licenses to users](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Stream. Ensure Stream isn't blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).

2. Stream で、ユーザーにライブ イベント作成の許可が割り当てられるようにします。 既定では、管理者は外部アプリまたはデバイスでイベントを作成できます。 Stream 管理者は、Stream で[ライブ イベントの作成を許可する他のユーザーを追加](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)できます。  

3. Stream 管理者によって設定されている会社のポリシーにライブ イベントの開催者が同意していることを確認します。Stream 管理者が[会社のガイドライン ポリシーを設定](https://docs.microsoft.com/stream/company-policy-and-consent)し、そのポリシーに同意してからでなければ従業員がコンテンツを保存できないようにしている場合、ユーザーは Teams で (外部アプリまたはデバイスを使用して) ライブ イベントを作成する前に、ポリシーに同意する必要があります。 組織でライブ イベント機能を展開する前に、このようなライブ イベントを作成するユーザーがポリシーに同意していることを確認してください。 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>手順 4: Teams でライブ イベント用のビデオ配信ソリューションを設定する

ライブ イベント ビデオの再生ではアダプティブ ビットレート ストリーミング (ABR) が使用されますが、これはユニキャスト ストリーミングであるため、すべての視聴者がインターネットから独自にビデオ ストリーミングを取得することになります。 ライブ イベントまたはビデオを組織の多数のユーザーに送信する場合、視聴者によって大量のインターネット帯域幅が消費される可能性があります。 組織がこのようなライブ イベントのインターネット トラフィックを削減できるように、ライブ イベント ソリューションには、Microsoft の信頼できるビデオ配信パートナーが提供する Software Defined Network (SDN) またはエンタープライズ コンテンツ配信ネットワーク (eCDN) が統合されています。 これらの SDN/eCDN プラットフォームを使用すると、組織はエンド ユーザーの視聴エクスペリエンスを犠牲にすることなく、ネットワーク帯域幅を最適化できます。 Microsoft パートナーのサポートを利用すると、エンタープライズ ネットワーク全体にわたるビデオ配信の拡張性と効率性をさらに高めることができます。

**Teams 外部のソリューションを購入してセットアップする** ビデオ配信をスケーリングする場合、Microsoft の信頼できるビデオ配信パートナーを利用して、エキスパートからのサポートを得ることができます。 ビデオ配信プロバイダーを有効にして Teams で使用するには、その前に Teams 外部の SDN/eCDN ソリューションを購入して、Teams とは別に設定する必要があります。

次の SDN/eCDN ソリューションは統合されており、Stream で使用されるように設定できます。

- **Hive Streaming** はライブのオンデマンド エンタープライズ ビデオ配信に対応する、シンプルで強力なソリューションです。 Hive はソフトウェアベースのソリューションであり、ハードウェアや帯域幅を追加する必要はありません。さらに、ネットワークに悪影響を与えることのない安全な方法で、数千人のユーザーが同時にビデオを視聴できるようにします。 SDN/eCDN ソリューションを購入する前にビデオがネットワークに与える影響について理解できるよう、Hive Streaming には Microsoft のお客様向けにブラウザーベースの分析ソリューションも用意されています。 [詳細については、こちらを参照してください](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective** はクラウドベースのスマートなピアリング配信プラットフォームです。既存のネットワーク インフラストラクチャを活用して、コンテンツをさまざまな形式 (ライブストリーミング ビデオ、オンデマンド ビデオ、ソフトウェア更新プログラム、セキュリティ パッチなど) でより高速かつ確実に、少ない帯域幅で配信します。 Microsoft のセキュリティで保護されたプラットフォームは、世界中の大手金融機関から信頼を得ています。追加のハードウェアは不要で、簡単にセットアップして保守できます。 [詳細については、こちらを参照してください](https://kollective.com/microsoft-pilot/)。
 
- **Ramp OmniCache** を利用すると、次世代のネットワーク配信ソリューションとして、グローバル WAN 全体にわたりシームレスにビデオ コンテンツを配信できます。イベント プロデューサーがネットワーク帯域幅を最適化し、ライブ イベントのブロードキャストとオンデマンド ストリーミングをサポートするのに役立ちます。 Teams で作成されるライブ イベント用の Ramp OmniCache のサポートは、間もなく利用可能になります。 [詳細については、こちらを参照してください](https://rampecdn.com)。 

- ネットワーク最適化の業界標準である**Riverbed**は、Microsoft Teams とストリーミングに対するアクセラレータソリューションを拡張しています。  Microsoft 365 のお客様は、チームやストリームなどのさまざまな先進企業 SaaS サービスとともに、信頼性の高い365トラフィックを迅速に加速して、どこからでも要員の生産性を向上させることができます。 チームとストリームの加速化は、あらゆる機能を備えた簡単なセットアップを通じて有効にすることができます。これには、世界クラスのさまざまなサポートと継続的な投資が含まれます。
 
> [!NOTE] 
> お客様が選択した SDN または eCDN ソリューションには、そのソリューションの使用を管理する、**サードパーティ プロバイダーのサービス利用規約とプライバシー ポリシー**が適用されます。 プロバイダーのソリューションの使用に対しては、Microsoft ボリューム ライセンス条項やオンライン サービス条項は適用されません。 **サードパーティ プロバイダーの利用規約**に同意しない場合は、Teams でそのソリューションを有効にしないでください。 

SDN または eCDN ソリューションをセットアップした後、Teams でのライブ イベント用にプロバイダーを構成できます。 

## <a name="next-steps"></a>次の手順

[Teams でライブ イベント設定を構成する](configure-teams-live-events.md)方法を確認する。

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
