---
title: "Office 365 の URL と IP アドレスの範囲 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 4f356a19ee7df9bd7a21867fdcbff6087a5b4aaa
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 の URL と IP アドレスの範囲
=====================================

正しく構成する必要のある IP とポートの詳細かつ最新のリストについては、「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)」をご覧ください。Microsoft は、Office 365 サービスの向上に継続的に取り組み、新しい機能を追加しています。そのため必須のポート、URL、IP アドレスが時間の経過とともに変更される場合があります。最新のポートやプロトコルに関するガイドについては、「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)」をご覧ください。[RSS 経由で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)して、エンドポイントが更新または変更されたときに通知を受信できるようにすることをお勧めします。

既に説明したとおり、Microsoft Teams の通話と会議は次世代のクラウドベースインフラストラクチャに基づいて構築されています。このインフラストラクチャは Skype および Skype for Business でも採用されています。この技術的投資には、メディア処理および信号用のAzure ベースのクラウド サービス、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワーク回復、テレメトリー、品質診断が含まれます。そのため、一部の必須 URL および IP は Skype と Skype for Business の両方に関連付けられている場合があります。

すべての Office 365 ワークロードについて、Microsoft Teams サービスへの推奨接続方法は、可能な場合に転送プロキシをバイパスする方法です。プロキシ サーバーがクライアントと Office 365 データセンター間に存在する場合は、UDP ではなく、メディアの品質が低下する TCP 上に強制される場合があります。トラフィック バイパスを構成するために使用できるサンプルのプロキシ PAC ファイルを「[Managing Office 365 endpoints (Office 365 エンドポイントの管理)](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a)」ガイドからダウンロードできます。

ネットワークおよびセキュリティ ポリシーで、Office 365 トラフィックがプロキシ サーバーを経由することが求められている場合は、Microsoft Teams を実稼動に展開する前に上記の要件を満たしていることを確認してください (詳しくは、「[Skype for Business Online 向けのプロキシ サーバー](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)」をご覧ください)。
