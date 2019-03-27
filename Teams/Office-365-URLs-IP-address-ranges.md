---
title: Office 365 の URL と IP アドレスの範囲
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e375452e236e38e036a5fe2413ba0848845587ab
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885815"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 の URL と IP アドレスの範囲
=====================================

Teams のために正しく構成されている必要がある URL、IP アドレス、ポート、およびプロトコルの詳細な最新のリストについては、「[Office 365 URL および IP アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)」をご覧ください。 マイクロソフトは、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Office 365 サービスを改善し、新機能を追加します。 お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。

Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。 これらのテクノロジへの投資には、メディアの処理と通知、H.264 ビデオ コーデック、絹および著作オーディオ コーデック、ネットワークの復元機能、遠隔測定、および品質診断の Azure ベースのクラウド サービスが含まれます。 したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。

すべての Office 365 ワークロードで、推奨される Teams サービスへの接続方法は、可能な場合にフォワード プロキシをバイパスすることです。 プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。 [Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)から、トラフィック バイパスを構成するために使用できるサンプルのプロキシ PAC ファイルをダウンロードします。

ネットワー キングとセキュリティ ポリシーには、Office 365 のトラフィックをプロキシ サーバー経由で配信が必要とする場合に、チームを (レビュー[チームやビジネス オンラインの Skype のプロキシ サーバー](proxy-servers-for-skype-for-business-online.md)を運用環境に展開する前に、上記の条件が既に満たされていることを確認します。参考)。
