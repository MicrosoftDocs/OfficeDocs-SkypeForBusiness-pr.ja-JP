---
title: Microsoft Teams に表示される
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: この記事では、Microsoft Teams のディスプレイでサポートされている機能の概要と機能について説明します。
ms.openlocfilehash: 18b8219a3eef391170c7321ae994d79f1b73f016
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268772"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams に表示される

Microsoft Teams ディスプレイは、アンビエント タッチスクリーンと Cortana を搭載したハンズフリー エクスペリエンスを備えた、1 つの専用 Teams デバイスのカテゴリです。 この記事では、Teams の表示の概要を説明し、組織内の Teams ディスプレイの計画、配信、管理に役立ちます。

Teams の表示では、お気に入りの Teams 機能&ndash;のチャット、会議、通話、予定表、ファイル&ndash;が 1 つのデバイスにまとめられます。 Teams ディスプレイを使用すると、ユーザーはマイク、カメラ、スピーカー (または Bluetooth ヘッドセット) を使用して、信頼性の高い通話と会議のエクスペリエンスを実現できます。 Teams ディスプレイは、ユーザーの Windows PC と統合され、シームレスなクロスデバイス操作を可能にするコンパニオン エクスペリエンスを提供します。

詳細については、「 [Teams の概要」の画面を参照](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)してください。

## <a name="features-supported-by-teams-displays"></a>Teams でサポートされている機能の表示

[Teams スマートフォンでサポートされている機能](phones-for-teams.md#features-supported-by-teams-phones)に加えて、次の機能は Teams の表示に固有です。

- **Teams 専用ディスプレイ** ユーザーは、チャット、会議、通話、チームとチャネル、ファイルなど、すべての主要な Teams 機能にアクセスできます。
- **アンビエント エクスペリエンス** ユーザーは、常にオンで目に見える表示で作業を簡単に把握し、主要な作業デバイスでコンテキストを切り替えずに重要なアクティビティや通知を表示できます。 ユーザーは、設定を使用して背景をカスタマイズすることで Teams の表示をカスタマイズすることもできます。
- **Cortana を使用したハンズフリー** ユーザーは自分の声を使って Teams のディスプレイを操作して、会議に簡単に参加して発表したり、Teams チャットへの返信を指示したり、予定表の内容を確認したりできます。
- **ロック画面にメモを残す** ゲストはオーディオ、ビデオ、テキストのノートを残すことができます。ユーザーはゲストが残したメモを確認し、誰が停止したかを確認できます。  

## <a name="required-licenses"></a>必要なライセンス

Teams ライセンスは[、Microsoft 365 および Office 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の一部として購入できます。 Teams ディスプレイを使用するために必要なライセンスの詳細については、「 [Microsoft Teams での音声通話とビデオ通話](https://products.office.com/microsoft-teams/voice-calling)」を参照してください。

Teams を取得する方法の詳細については、Microsoft Teams [にアクセス操作方法確認してください。](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Intuneを使用して Teams ディスプレイを展開する

Intuneを使用して Teams ディスプレイを展開する方法の詳細については、「[Teams の電話と Teams の展開」を参照](phones-displays-deploy.md)してください。

## <a name="manage-teams-displays-in-your-organization"></a>組織内の Teams の表示を管理する

Teams ディスプレイ デバイスを管理するには、Microsoft Teams 管理センターの左側のナビゲーションで Teams の表示に移動 **します**。 ここから、デバイス構成プロファイルの変更、更新の管理、デバイスの再起動、デバイス タグの追加と削除などを行うことができます。 詳細については、「 [Teams でデバイスを管理する](device-management.md)」を参照してください。

## <a name="set-up-hot-desking-on-teams-displays"></a>Teams ディスプレイにホット デスクを設定する

ホット デスクは、組織内のユーザーが Teams と Outlook を介して、またはデバイス自体から事前に一時的なワークスペースを予約できるようにします。 ホット デスクが有効になっている場合、ユーザーは Microsoft 365 資格情報を使用して Teams にサインインし、会議、チャット、ファイルにアクセスします。 サインアウトすると、すべての個人情報がデバイスから削除されます。

開始するには、Microsoft Teams Rooms Standard ライセンスを取得し、Teams ディスプレイごとにリソース アカウントを作成する必要があります。 [リソース アカウントを作成するための会議室と共有 Teams デバイスの](../rooms/with-office-365.md)リソース アカウントの作成に関する説明を参照してください。

リソース アカウントを作成したら、ホット デスクを有効にするポリシーを作成して割り当てることができます。 詳細については、「 [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 」を参照してください。

> [!IMPORTANT]
> ホット デスクを使用した Teams ディスプレイは複数のユーザーによって共有ワークスペースで使用されるため、環境内の条件付きアクセス 規則やその他の ID 構成 (Multi-Factor Authentication など) は、これらのデバイスに影響を与え、サインインの問題を引き起こす可能性があります。 共有デバイスのセキュリティ保護に関するガイダンスについては、 [共有 Teams Android デバイスの認証のベスト プラクティス](authentication-best-practices-for-android-devices.md)に関するページを参照してください。

## <a name="upgrade-teams-phones-to-teams-displays"></a>Teams の電話を Teams にアップグレードする画面

Teams ディスプレイは Teams スマートフォンの進化です。 Microsoft Teams 管理センターを使用して、組織内の Teams Phone を Teams ディスプレイにアップグレードできます。 このオプションは、Teams ディスプレイへのアップグレードをサポートする電話でのみ使用できます。 詳細については、「 [Teams の電話を Teams にアップグレードする」の画面を参照](upgrade-phones-to-displays.md)してください。

## <a name="see-also"></a>関連項目

[Microsoft Teams のディスプレイの概要](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[TEAMS に IP Phone をアップグレードするディスプレイ](upgrade-phones-to-displays.md)

[Teams での Cortana 音声アシスタンス](../cortana-in-teams.md)