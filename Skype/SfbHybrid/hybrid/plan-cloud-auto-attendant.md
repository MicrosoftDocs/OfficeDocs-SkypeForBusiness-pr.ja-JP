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
ms.openlocfilehash: f0b8018e7a926444e7920ccac31ed3ff4ab5c15f
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510806"
---
# <a name="plan-cloud-auto-attendants"></a>クラウド自動応答を計画する

Exchange ユニファイドメッセージング (Exchange Server 2013 または Exchange Server 2016) で使用される自動応答は、Exchange Server 2019 または Exchange Online では使用できなくなりました。 Skype for Business Server 2019 の実装が、これらのいずれかの Exchange バージョンと統合されている場合は、電話システムに関連付けられているオンラインクラウド音声機能を使用する必要があります。 Exchange server 2013 および2016に所属する Exchange UM サービスをクラウドに移行する方法については、「 [Plan For Skype For Business server And Exchange server migration](plan-um-migration.md) 」を参照してください。

これは本質的に、自動応答などのユニファイドメッセージング機能を使用したい場合に、Skype for Business Server 2019 のハイブリッド実装を行うことを意味します。 詳細については[、「Skype For Business Server と Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)」を参照してください。

自動応答は、お客様の電話を受け付け、案内応答を再生し、メニューオプションを提供し、音声またはダイヤルパッドを使用して発信者と対話して、呼び出しを正しい宛先にルーティングするクラウドサービスです。 各自動応答には、Microsoft Teams 管理センターの自動応答に直接リンクされる Skype for Business Server 2019 システムの*リソースアカウント*(「[リソースアカウントの構成](configure-onprem-ra.md)」を参照) が割り当てられます。 自動応答に関する詳細については、「[クラウド自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)」を参照してください。自動応答にはどのようなオプションと機能がありますか。

> [!NOTE]
> 複数の Microsoft サービス番号、直接ルーティング番号、またはハイブリッド番号を自動応答に割り当てることができます。

クラウド自動応答への着信は、次に示すように、いくつかのパスのいずれかを受け取ることができます。

![自動応答の図](../../SfBServer2019/media/AA-plan-concept.png)

1. Skype for Business Server 2019 経由
2. [セッションボーダーコントローラー](/MicrosoftTeams/direct-routing-border-controllers.md)と[直接ルーティング](/MicrosoftTeams/direct-routing-plan.md)を介して
3. Office 365 でオンラインになっている番号を使用します。

以下も参照してください。

- [クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)
- [着信呼び出しへの自動応答とルーティング](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requirements

次の要件は、サポートされているトポロジで Skype for Business Server 2019 が既に展開されていることを前提としています。  要件は、シナリオによって異なります。

- 既に Exchange UM online またはオンプレミスを使用していて、Skype for Business 2019 にアップグレードする場合は、自動応答の構造をキャプチャし、クラウドの自動応答を使用してクラウドで再作成する必要があります。 詳細については、「 [EXCHANGE UM 自動応答またはコールキューを電話システムに移行する](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)」を参照してください。

- クラウド自動応答の新しい構成については、「 [Configure resource accounts](configure-onprem-ra.md)」に記載されている手順に従ってください。

上記の要件に加えて、次の要件を構成して、Microsoft クラウド自動応答サービスに接続する必要があります。

- ハイブリッド接続。 Skype for Business Server を既に展開しており、オンプレミスのユーザーに対してクラウドの自動応答を有効にする場合は、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。 これは、分割ドメイン構成と呼ばれることがあります。

   詳細については、「skype for business [server と office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。

- 自動応答に電話番号を割り当てる場合は、 [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)ライセンスが必要です。
- 各自動応答に対してオンライン[リソースアカウント](/MicrosoftTeams/manage-resource-accounts.md)または社内[リソースアカウント](configure-onprem-ra.md)を作成し、電話番号とライセンスを割り当てます。 

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、自動応答を引き続きサポートするように、移行を慎重に計画する必要があります。 以下の点に注意します。

- Exchange Server 2019 が Exchange UM 機能を提供しなくなった
- Exchange ユニファイドメッセージングは、定年モードになっています
- Skype for Business Server 2019 が Exchange Online UM と統合されなくなりました

クラウド自動応答は、Skype for Business Server 2019、2015、および2013を使用して構成できます。

Microsoft では、次の移行パスをお勧めします。

- Skype for Business Server 2019 にアップグレードする場合は、exchange Server 2013 または2016で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は、クラウドの自動応答にアップグレードする必要があります。

- Exchange Server 2019 にアップグレードしていて、以前のバージョンの Exchange Server UM を Skype for Business Server voice messaging に対して使用している場合は、メールボックスをアップグレードする前に、Skype for Business Server 2019 にアップグレードすることをお勧めします。  それ以外の場合、音声メッセージング機能は失われます。

移行の計画の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>以前に実装された Exchange UM 自動応答システムを移行する

現時点では、Exchange 2013 または2016で作成された UM 自動応答システムのクラウドへの自動移行はサポートされていません。 自動応答システムを手動で再作成するには、次の操作を行う必要があります。

1. Exchange 管理者の powershell コマンドを使用して、ネストされた自動応答と呼び出しキューを含む、古い自動応答システムの構造を確認します。  
2. 各 UM 自動応答ノードに関連付けられている音声合成スクリプトまたは録音済みメッセージのコピーを作成します。
3. テスト電話番号とライセンスをオブジェクトに割り当てることを含め、各自動応答ノードに対してオンプレミスエンドポイントを作成します。 電話システムのようなオンラインサービスで使用される、オンプレミスの電話番号ライセンスを割り当てることができるようになりました。
4. Skype for Business Online と電話システムを使用して、新しいクラウド自動応答サービスを実装します。 実装の詳細については、「 [Configure resource accounts](configure-onprem-ra.md) 」を参照してください。 この場合は、各 UM 自動応答ノードに関連付けられている音声合成スクリプトまたは録音済みメッセージをアップロードします。
5. クラウド自動応答の機能をテストします。
6. 古い Exchange UM 自動応答に割り当てられている電話番号を、新しく作成したメインクラウド自動応答に再割り当てします。

これらの手順の詳細について[は、「EXCHANGE UM 自動応答またはコールキューを電話システムに移行する](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)」を参照してください。

## <a name="additional-planning-resources"></a>その他の計画に関するリソース

「 [Small business の例-自動応答の設定](/microsoftteams/tutorial-org-aa)」というタイトルのチュートリアルでは、ユーザーのニーズに関する情報の収集、自動応答とユーザーの構成 (および場合によっては呼び出しキュー) の計画、メニュープロンプトの作成、Teams 管理センターでのプランの実装を行います。 チュートリアルを確認し、そこにある演習を使用して計画を作成します。

お客様のニーズを満たす堅固な構造を持っていて、顧客に効率的に対応するスクリプトを実行している場合は、「[リソースアカウントを構成](configure-onprem-ra.md)する」に進みます。

> [!CAUTION]
> [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)で説明したように、サーバー2015で作成された Exchange UM 自動応答をサーバー2019を実行しているサーバーに移動しないことをお勧めします。 そのため、その時間は共存モードで実行されている Skype for business Server 2015 プールに保持する必要があります。

## <a name="see-also"></a>関連項目

[Skype for Business Server および Exchange Server の移行を計画する](plan-um-migration.md)

[リソースアカウントを構成する](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM:[着信呼び出しへの自動応答とルーティング](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Skype for Business Server と Office 365 の間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[Skype for Business Server と Office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)

[KB4480742: contact オブジェクトを Skype for Business Server 2019 に移動した後、fast busy および "500 Server Internal" エラーが発生し、サブスクライバーアクセスまたは自動応答への呼び出しが失敗する](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
