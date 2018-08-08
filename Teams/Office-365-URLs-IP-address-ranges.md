---
title: Office 365 の URL と IP アドレスの範囲
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f946bc45fae230c0fd0ead9c06d0ced537bc7f92
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998974"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 の URL と IP アドレスの範囲
=====================================

Url、IP アドレス、ポート、およびチームを正しく構成する必要があるプロトコルの詳細で最新の状態の一覧については、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)を移動します。 マイクロソフトが継続的に Office 365 のサービスを向上させることし、新しい機能を追加するには、必要なポート、Url、つまり時間の経過と共に IP アドレスを変更することがあります。 そのを[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。 この情報を更新または変更されたときに通知を受信します。

通話や会議の経験は、次世代クラウド ・ ベースのインフラストラクチャがまた使用する Skype、Skype ビジネスの上に構築されたチームです。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 ように、Url が存在し、必要な可能性のあるは ip アドレス、Skype と Skype のビジネスの両方に関連付けられています。

、Office 365 のすべてのワークロードの可能な場合はチームのサービスに推奨される接続方法がフォワード プロキシをバイパスするが。 プロキシ サーバーは、クライアントと Office 365 のデータ ・ センターとの間に配置、ときに UDP では、メディアの品質に影響するのではなく TCP 経由でメディアが強制される可能性があります。 [Office 365 の管理のエンドポイント](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)からのトラフィックのバイパスの構成に使用できるサンプル プロキシの PAC ファイルをダウンロードします。

ネットワー キングとセキュリティ ポリシーには、Office 365 のトラフィックをプロキシ サーバー経由で配信が必要とする場合は、チームを運用環境に展開する前に、上記の条件が既に満たされていることを確認してください (の[オンライン ビジネスの Skype のプロキシ サーバー](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)を確認します。ガイダンス)。
