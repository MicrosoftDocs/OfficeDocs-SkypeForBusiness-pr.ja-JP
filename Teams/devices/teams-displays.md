---
title: Microsoft Teams表示
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: この記事では、ディスプレイでサポートされる機能と機能の概要Microsoft Teamsします。
ms.openlocfilehash: 8c8004edd12042ca27e77e545f23b8770f8d1899
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926330"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams表示

Microsoft Teamsディスプレイは、環境タッチスクリーンと、Cortana を利用したハンズフリーエクスペリエンスを備える、1 つの専用 Teams デバイスのカテゴリです。 この記事では、Teamsの概要を説明し、組織内のTeamsを計画、配信、管理するのに役立ちます。

Teamsでは、お&ndash;気に入りの機能Teamsチャット、会議&ndash;、通話、予定表、ファイルを 1 つのデバイスにまとめます。 このTeamsを使用すると、ユーザーはマイク、カメラ、スピーカー (またはヘッドセットBluetooth) を使用して、信頼性の高い通話と会議のエクスペリエンスを実現できます。 Teamsディスプレイは、ユーザーの PC Windows統合され、デバイス間のシームレスな対話を可能にするコンパニオン エクスペリエンスを実現します。

詳細については、「Get [started with Teams displays」を参照してください](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)。

## <a name="features-supported-by-teams-displays"></a>各ディスプレイでサポートTeams機能

携帯電話でサポート[される](phones-for-teams.md#features-supported-by-teams-phones)機能に加Teams、次の機能は、スマートフォンのディスプレイTeamsです。

- **Teams 専用ディスプレイ ユーザー** は、チャット、会議、Teams、チームとチャネル、ファイルなどのすべての主要な機能にアクセスできます。
- **環境エクスペリエンス** ユーザーは、常にオンと一目で確認できるディスプレイを使用して作業を簡単に把握し、主要な作業デバイスでコンテキストを切り替えることなく、重要なアクティビティや通知を表示できます。 ユーザーは、設定を使用Teamsをカスタマイズすることで、ユーザーをカスタマイズして表示することもできます。
- **Cortana** のハンズフリー ユーザーは、音声を使って Teams ディスプレイと対話し、会議に簡単に参加して発表したり、Teams チャットへの返信をディクテーションしたり、予定表の内容を確認したりすることができます。
- **ロック画面にメモを残す** ゲストは音声、ビデオ、テキストのノートを残し、ユーザーはゲストが残したノートを確認し、誰が停止したのか確認できます。  

## <a name="required-licenses"></a>必要なライセンス

Teamsライセンスは、サブスクリプションの一部としてMicrosoft 365購入Office 365[できます](/office365/servicedescriptions/teams-service-description)。 ディスプレイを使用するために必要なライセンスの詳細については、「Teamsでの音声通話とビデオ通話」[を参照Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling)。

アカウントを取得する方法の詳細についてはTeamsアクセスを取得する[方法に関するMicrosoft Teams。](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Intune をTeamsディスプレイをデプロイする

Intune を使用してディスプレイをデプロイする方法のTeams、「電話とディスプレイを展開Teams[する」をTeamsしてください](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>組織内Teams表示を管理する

デバイスの表示Teams管理するには、管理センターの左側のナビゲーションMicrosoft Teams、[ディスプレイ] Teams **します**。 ここから、デバイス構成プロファイルの変更、更新の管理、デバイスの再起動、デバイス タグの追加と削除を行えます。 詳細については、「デバイスを管理[する」を参照Teams](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>ディスプレイでホット デスクをTeamsする

ホット デスク機能を使用すると、組織内のユーザーは、Teams と Outlook またはデバイス自体から事前に一時的なワークスペースを予約できます。 ホット デスクが有効になっている場合、ユーザーは会議、チャット、Teamsにアクセスするための Microsoft 365 資格情報を使用して表示されるメッセージにサインインします。 サインアウトすると、すべての個人情報がデバイスから削除されます。

開始するには、Rooms Standard ライセンスを取得し、Microsoft Teams表示ごとにリソース アカウントを作成Teamsがあります。 リソース アカウント[を作成Microsoft Teamsを使用Office 365会議室](../rooms/with-office-365.md)のデプロイに関するページを参照してください。

リソース アカウントを作成した後、ポリシーを作成して割り当て、ホット デスクを有効にできます。 詳細 [については、「New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 」を参照してください。

> [!IMPORTANT]
> ホット デスク付きの Teams ディスプレイは複数のユーザーによって共有ワークスペースで使用されます。条件付きアクセス ルールと、Multi-Factor Authentication などの環境内の他の ID 構成は、これらのデバイスに影響を与え、サインインの問題を引き起こす可能性があります。 共有デバイスのセキュリティ保護に関するガイダンスについては、「共有デバイスと Android デバイスの認証[のベスト プラクティスTeams参照してください](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>スマートフォンTeamsディスプレイにTeamsする

Teamsディスプレイは、スマートフォンの進化Teamsです。 組織内のTeamsをアップグレードして、Teamsを使用してMicrosoft Teams表示することができます。 このオプションは、ディスプレイへのアップグレードをサポートしている電話Teams使用できます。 詳細については、「スマートフォンをディスプレイに[TeamsアップグレードするTeams参照してください](upgrade-phones-to-displays.md)。

## <a name="see-also"></a>関連項目

[新しいMicrosoft Teamsの紹介](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[IP 電話をディスプレイにTeamsする](upgrade-phones-to-displays.md)

[Cortanaでの音声アシスタンスのTeams](../cortana-in-teams.md)