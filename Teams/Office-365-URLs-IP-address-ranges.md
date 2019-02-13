---
title: Office 365 の URL と IP アドレスの範囲
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11b874b3c42fa62889eb8c2bf8c9633d612c875a
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "29964343"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 の URL と IP アドレスの範囲
=====================================

Url、IP アドレス、ポート、およびチームを正しく構成する必要があるプロトコルの詳細で最新の状態の一覧については、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を移動します。 マイクロソフトは、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Office 365 サービスを改善し、新機能を追加します。 そのを[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。 この情報を更新または変更されたときに通知を受信します。

通話や会議の経験は、次世代クラウド ・ ベースのインフラストラクチャがまた使用する Skype、Skype ビジネスの上に構築されたチームです。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 ように、Url が存在し、必要な可能性のあるは ip アドレス、Skype と Skype のビジネスの両方に関連付けられています。

、Office 365 のすべてのワークロードの可能な場合はチームのサービスに推奨される接続方法がフォワード プロキシをバイパスするが。 プロキシ サーバーは、クライアントと Office 365 のデータ ・ センターとの間に配置、ときに UDP では、メディアの品質に影響するのではなく TCP 経由でメディアが強制される可能性があります。 [Office 365 の管理のエンドポイント](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)からのトラフィックのバイパスの構成に使用できるサンプル プロキシの PAC ファイルをダウンロードします。

ネットワー キングとセキュリティ ポリシーには、Office 365 のトラフィックをプロキシ サーバー経由で配信が必要とする場合に、チームを (レビュー[チームやビジネス オンラインの Skype のプロキシ サーバー](proxy-servers-for-skype-for-business-online.md)を運用環境に展開する前に、上記の条件が既に満たされていることを確認します。参考)。
