---
title: "クイック スタート ガイド - Microsoft チームのプランの呼び出しを構成します。"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Microsoft のチームで通話プランを構成するためのクイック スタート ガイド"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e38317132190b3035f37509d1fa7b2da5e4785c7
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>クイック スタート ガイド: Microsoft チームのプランの呼び出しを構成します。
==============================================================

このガイドはできる一連の上のユーザーと実行しているので、チームのプランの呼び出しを確認することができます。

チームのプランの呼び出しの 2017、12 月 12日お知らせを読む:[インテリジェント通信チーム呼び出しには、次の手順を移動します。](https://aka.ms/ipyqus)

> [!NOTE]
> 、このクイック スタート ガイドと並行、使用すること、[実用的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)や[FastTrack](https://aka.ms/cloudvoice)を計画し、正常に展開することをお勧めします。

-[Skype for Business で、Office 365 機能 - プランの呼び出しを追加して land 線と公衆交換電話網 (PSTN) を使って携帯電話の電話の発信や受信にチームを使用することができます。

![チーム呼び出し](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>チームでは、[**通話**] タブを有効にするための前提条件
チームでは、[**通話**] タブを有効にし、ユーザーが PSTN 通話を送受信できるようにする、ユーザーのプロビジョニングを電話システムとプランの呼び出しの必要があります。これをセットアップする方法については、[プランの呼び出しを設定する](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)をご覧ください。

> [!IMPORTANT]
> プランの呼び出しを設定する、チームで、前に注意してください次の制限事項。
> * **ハイブリッド音声は、チームでサポートされていない**ハイブリッド ボイスは現在サポートされていませんチームでします。ハイブリッド音声顧客がサービス中断これにより、チームで通話を受信するポリシーのいずれかを変更するのにはお勧めできません。
> * **チームでは、フェデレーションの通話はサポートされていない**(テナント/会社間での呼び出し) フェデレーション通話は現在サポートされていませんチームでします。フェデレーションの着信通話、チームでサポートされているまでを構成する方法に関係なく、Skype for Business に常にルーティングされます。

## <a name="teams-interop-policy-configuration"></a>チームの相互運用ポリシーの構成
チームが着信を受信し始めますを有効にする必要がありますチームの相互運用ポリシーを更新する、skype for Business リモート Windows PowerShell セッションを使用して[`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)チームに着信をリダイレクトするのには、コマンドレットします。チームの相互運用ポリシーの詳細については、 [Microsoft チーム」と「Skype for Business の相互運用性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)を参照してください。

> [!TIP]
> 必要がある PowerShell コマンドレットを検索するには、 [Skype for Business PowerShell コマンドレットのドキュメント](https://docs.microsoft.com/powershell/module/skype)で**フィルター** ] ボックスに"CsTeamsInteropPolicy"を入力します。

### <a name="default-teams-interop-policy"></a>チームの既定の相互運用ポリシー
チームが、既定のポリシー設定を既存のビジネス ワークフローがチーム展開中に中断されないように設計されています。既定では、VoIP、PSTN とフェデレーションの呼び出しをユーザーに引き続きチームに着信通話を有効にするポリシーを更新するまでに Skype for Business にルーティングされます。これによりがないこと意図しない音声サービス中断を開始するパイロット チームを展開するとします。

チームの相互運用ポリシーには、次の既定の構成がされています。

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

既定の構成の動作は次のとおりです。
* **既存の Skype for Business ユーザーに**、このポリシーが対応している、Skype for Business 通話は Skype for Business に転送され、チーム呼び出しはチームに転送されることを確認します。PSTN とフェデレーションの呼び出しが開かれ Skype for Business このポリシーが有効な場合。
* **Skype for Business の場合**、チームのユーザーの通話のほか、PSTN 通話の発信のみをチームで使われます。チームで PSTN 通話を受けるには、ユーザーに割り当てられているチームの相互運用ポリシーを変更する必要があります。

> [!NOTE]
> 電話システムとプランの呼び出しライセンスでプロビジョニングされているユーザーと使用する skype for Business Online では、既定のグローバル チーム相互運用ポリシーを使用して構成されたチームで有効になっている [通話] タブが表示されますをチームからの送信の PSTN 電話をかけることができます。管理者が管理の操作を実行することなしです。

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>既定のポリシーを使用してチームを構成する方法
既定では、テナントのすべてのユーザーにグローバル チームの相互運用ポリシーを適用し、上記の説明に従って、既定の設定で構成します。何らかの理由をユーザーに別のポリシーを与えたいし、考えての既定の設定に戻すには場合、は、リモートの Windows PowerShell セッションをビジネス用 Skype でグローバル チーム相互運用ポリシーを適用する必要があります。

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> 既定値からグローバル チームの相互運用ポリシーを変更することはできますが、お強く推奨に対してします。 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>チームが着信 PSTN 通話を受けるを構成します。
PSTN 通話の着信を受信するには、チームでに既定値を使用してチームの相互運用ポリシーを適用してアプリケーションを呼び出すとチームを構成する必要があります`CallingDefaultClient`チームにパラメーターを設定します。

> [!IMPORTANT]
> ユーザーをチームで魅力的な新しい通話機能を使ってみるを広げる組織レベルの変更を加えるよりも前の初期セットには、この設定を適用することをお勧めします。

次事前構成されたチームの相互運用ポリシーを使用してチーム呼び出し着信 PSTN をルーティングすることを検討してください。

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

このポリシーの動作、次のとおりです。
* **既存の Skype for Business ユーザーに**、このポリシーが対応しているチームの着信通話をリダイレクトします。これには、(チームと Skype for Business) から VoIP と PSTN 通話の両方が含まれます。フェデレーションの通話は引き続き Skype for Business で受信します。 
* **Skype for Business の場合**と実際には、PSTN 通話が受信するチームでします。フェデレーションの通話は、現在チームでは**サポートされていません**。

> [!WARNING]
> 現時点では、変更する`CallingDefaultClient`チームにも影響 skype 通話ビジネス IP 電話用します。着信通話られ、携帯電話に受信できませんが、リング チーム クライアントのみをされます。既存の認定 SIP 電話のサポートについては、 [Skype for Business に Microsoft チーム機能ロードマップ](https://aka.ms/skype2teamsroadmap)を参照してください。

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>PSTN 通話を受けるチームを構成する方法
チーム呼び出しをリダイレクトするのには、リモートの Windows PowerShell セッションをビジネス用 Skype で上記のように、チームの相互運用ポリシーを適用します。

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>ユーザーに、好みの呼び出しのエクスペリエンスを変更できるようにチームを構成します。
有効にするカスタム チーム相互運用ポリシーの作成に必要なチームまたは Skype for Business で通話を受信するかどうかは、好みの呼び出し元エクスペリエンスをユーザーが独自の判断できるように、`AllowEndUserClientOverride`パラメーターします。

次には、好みの呼び出し元エクスペリエンスのユーザーの選択を有効にするチームの相互運用ポリシーの例を示します。

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

このユーザー設定のポリシーを適用するには、ユーザーに、好みの呼び出し元のアプリケーションを変更するオプションは自体を変更するユーザーのチーム クライアントでは使用されます。

![好みの呼び出し元アプリケーション オプション](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> 幅または組織レベルを変更する前にユーザーの初期セットには、この設定を適用することをお勧めします。

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>作成してチームのユーザー設定の相互運用ポリシーを適用する方法
チームのユーザー設定の相互運用ポリシーを作成するには、リモートの Windows PowerShell セッションをビジネス用 Skype で上記のように、次の手順に従います。

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>関連項目
[プランの呼び出しを設定します。](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Microsoft チーム」と「Skype for Business の相互運用性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[電話システムで Microsoft チームで通話プランに関する実用的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell コマンドレット リファレンス](https://docs.microsoft.com/powershell/module/skype)

[チームの PowerShell コマンドレット リファレンス](https://docs.microsoft.com/powershell/module/teams)
