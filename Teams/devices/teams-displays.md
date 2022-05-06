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
description: この記事では、Microsoft Teams ディスプレイでサポートされる機能の概要と機能について説明します。
ms.openlocfilehash: 77af5392b539045cdbacda2d6c278d35098437ed
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514680"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams表示

Microsoft Teamsディスプレイは、アンビエント タッチスクリーンとCortanaを利用したハンズフリーエクスペリエンスを備えた、1 つの専用Teams デバイスのカテゴリです。 この記事では、Teamsディスプレイの概要を説明し、組織内のTeamsディスプレイの計画、配信、管理に役立ちます。

Teams表示では、お気に入りのTeams機能&ndash;チャット、会議、通話、予定表、filesinto&ndash; が 1 つのデバイスにまとめられます。 Teamsディスプレイを使用すると、ユーザーはマイク、カメラ、スピーカー (またはヘッドセットBluetooth) を使用して、信頼性の高い通話と会議のエクスペリエンスを実現できます。 Teamsディスプレイは、ユーザーのWindows PC と統合され、シームレスなデバイス間の対話を可能にするコンパニオン エクスペリエンスをもたらします。

詳細については、[Teamsディスプレイの概要](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)を確認してください。

## <a name="features-supported-by-teams-displays"></a>Teamsディスプレイでサポートされている機能

[Teams電話でサポートされている機能](phones-for-teams.md#features-supported-by-teams-phones)に加えて、次の機能はTeamsディスプレイに固有です。

- **Teams ユーザー専用ディスプレイ** は、チャット、会議、通話、チーム、チャネル、ファイルなど、すべてのコア Teams機能にアクセスできます。
- **アンビエント エクスペリエンス** ユーザーは、常にオンで目に見える表示で作業を簡単に把握し、主要な作業デバイスでコンテキストを切り替えずに重要なアクティビティや通知を表示できます。 ユーザーは、設定を使用して背景をカスタマイズすることで、Teamsディスプレイをカスタマイズすることもできます。
- **ユーザーは、Cortanaとハンズフリー** で、音声を使用してTeamsディスプレイと対話して、会議に簡単に参加してプレゼンテーションしたり、Teams チャットに対する返信を指示したり、予定表の内容を確認したりできます。
- **ロック画面にメモを残す** ゲストはオーディオ、ビデオ、テキストのノートを残すことができます。ユーザーはゲストが残したメモを確認し、誰が停止したかを確認できます。  

## <a name="required-licenses"></a>必要なライセンス

Teams ライセンスは、[Microsoft 365サブスクリプションとOffice 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の一部として購入できます。 Teamsディスプレイを使用するために必要なライセンスの詳細については、「[Microsoft Teamsでの音声通話とビデオ通話](https://products.office.com/microsoft-teams/voice-calling)」を参照してください。

Teamsを取得する方法の詳細については、Microsoft Teams[にアクセス操作方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)確認してください。

## <a name="deploy-teams-displays-using-intune"></a>Intuneを使用してTeamsディスプレイをデプロイする

Intuneを使用してTeamsディスプレイを展開する方法の詳細については、「[Teams電話とTeamsディスプレイを展開する](phones-displays-deploy.md)」を参照してください。

## <a name="manage-teams-displays-in-your-organization"></a>組織内のTeams表示を管理する

Teamsディスプレイ デバイスを管理するには、Microsoft Teams管理センターの左側のナビゲーションで、**Teamsディスプレイ** に移動します。 ここから、デバイス構成プロファイルの変更、更新の管理、デバイスの再起動、デバイス タグの追加と削除などを行うことができます。 詳細については、「[Teamsでデバイスを管理する](device-management.md)」を参照してください。

## <a name="set-up-hot-desking-on-teams-displays"></a>Teamsディスプレイでホット デスクを設定する

ホット デスクを使用すると、組織内のユーザーは、TeamsとOutlook、またはデバイス自体から事前に一時的なワークスペースを予約できます。 ホット デスクが有効になっている場合、ユーザーは自分のMicrosoft 365資格情報を使用してTeamsにサインインして、会議、チャット、ファイルにアクセスします。 サインアウトすると、すべての個人情報がデバイスから削除されます。

開始するには、Microsoft Teams Rooms Standard ライセンスを取得し、Teams表示ごとにリソース アカウントを作成する必要があります。 [リソース アカウントを作成するには、「会議室と共有Teamsデバイスの](../rooms/with-office-365.md)リソース アカウントを作成する」を参照してください。

リソース アカウントを作成したら、ホット デスクを有効にするポリシーを作成して割り当てることができます。 詳細については、「 [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 」を参照してください。

> [!IMPORTANT]
> ホット デスクを使用したTeamsディスプレイは複数のユーザーによって共有ワークスペースで使用されるため、多要素認証などの環境内の条件付きアクセス 規則やその他の ID 構成は、これらのデバイスに影響を与え、サインインの問題を引き起こす可能性があります。 共有デバイスのセキュリティ保護に関するガイダンスについては、「[共有Teams Android デバイスの認証のベスト プラクティス](authentication-best-practices-for-android-devices.md)」を参照してください。

## <a name="upgrade-teams-phones-to-teams-displays"></a>Teams電話をTeamsディスプレイにアップグレードする

Teamsディスプレイは、Teams電話の進化です。 Microsoft Teams管理センターを使用して、組織内のTeams電話をTeamsディスプレイにアップグレードできます。 このオプションは、Teams ディスプレイへのアップグレードをサポートする電話でのみ使用できます。 詳細については、「[Teams電話をTeamsディスプレイにアップグレードする](upgrade-phones-to-displays.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Microsoft Teamsディスプレイの概要](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[IP Phone を Teams ディスプレイにアップグレードする](upgrade-phones-to-displays.md)

[Teamsで音声アシスタンスをCortanaする](../cortana-in-teams.md)