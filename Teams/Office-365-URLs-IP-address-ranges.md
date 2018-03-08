---
title: "Office 365 の Url と IP アドレス範囲"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "転送プロキシをバイパス Microsoft チーム サービス、およびネットワークとセキュリティ ポリシーの要件との接続の使用可能な場合は、適切に Office 365 の Url と IP アドレスの範囲を構成する方法について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 73bcce4ec670f79547d8d5ee24d8e3dcec14e52b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 の Url と IP アドレス範囲
=====================================

レビューの正確な ip アドレスの詳細と最新リストについては、次のリンク、正しく構成する必要があるポートをしてください: [Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)。Microsoft が常に、Office 365 サービスを改善し、追加する新機能と、そのため、必要なポート、Url と IP アドレスが経時変化します。、ポートとプロトコルの最新バージョンの[Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)のガイドを参照してください。強くお勧め[RSS を介して](https://go.microsoft.com/fwlink/p/?linkid=236301)購読エンドポイントの更新または変更されたときに通知を受信します。

前述のように、Microsoft チーム通話と会議のエクスペリエンスは次世代クラウド ベース インフラストラクチャも使用 Skype と Skype for Business に開発されています。これらの技術投資には、メディアの通知を処理し、H.264 ビデオ コーデック、絹と著作オーディオ コーデック、ネットワークの復元が、テレメトリと品質診断 Azure ベースのクラウド サービスが含まれます。Url があるし、いる ip アドレスに必要な可能性のあるように、Skype for Business と Skype の両方に関連付けられます。

すべての Office 365 ワークロードのチームの Microsoft サービスに推奨される接続方法をバイパスする転送プロキシ可能なします。クライアントと Office 365 のデータ センターのプロキシ サーバーが入力されているときに、メディアの品質に影響を与えるには、UDP ではなく TCP 経由でメディアが強制される可能性があります。トラフィック バイ パスを構成するのには使用できるサンプル プロキシ PAC ファイル[を管理する Office 365 エンドポイント](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a)のガイドをダウンロードできます。

ネットワークとセキュリティ ポリシーには、プロキシ サーバーで Office 365 のトラフィックが必要がある場合、[ことを確認を運用 (校閲[プロキシ サーバーを skype for Business Online に Microsoft チームを展開する前に、上記の要件が既に満たされています。](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)ガイダンス)。
