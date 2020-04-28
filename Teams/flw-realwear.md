---
title: RealWear 用 Microsoft Teams クライアントの IT 管理情報 (プレビュー)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: RealWear 用 Microsoft Teams クライアントの IT 管理チュートリアル。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec30e455a79ee37a107509e7c179dd859732b1e
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780576"
---
# <a name="microsoft-teams-for-realwear"></a>RealWear 用 Microsoft Teams

> [!NOTE]
> これはプレビューまたは先行リリースの機能です。

この記事では、RealWear ヘッドマウント ウェアラブルを使うための Microsoft Teams クライアントについて説明します。 RealWear の HMT-1 や HMT-1Z1 を使う第一線の作業員が、Teams のビデオ通話を使って遠隔地にいるエキスパートと共同作業ができるようになりました。 RealWear 用 Teams では、音声制御のユーザー インターフェイスにより現場作業員が100% ハンズフリーの状態を維持し、これにより騒音があり危険な環境でも状況認識を確保することができます。 現場作業員が見ている光景をリアルタイムで見せることによって、問題解決までの時間を短縮し、コストのかかるダウンタイムのリスクを軽減することができます。

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a>RealWear 用 Microsoft Teams の展開方法

RealWear 用 Microsoft Teams クライアントは現在、パブリック プレビュー中です。 このプレビューに参加するには、次のものが必要です。

リリース 10.5.0 以降に更新された RealWear デバイス。 詳細情報については、[こちら](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/)を参照してください。

> [!IMPORTANT]
> [こちら](https://www.realwear.com/solutions/microsoft-teams/#C1)で登録すると、「[RealWear の展望](https://cloud.realwear.com/)」で RealWear クライアント向けの Teams にアクセスすることができます。

## <a name="required-licenses"></a>必要なライセンス

Microsoft Teams ライセンスは、Microsoft 365 サブスクリプションおよび Office 365 サブスクリプションに含まれています。 RealWear 用 Teams を使用するために、追加のライセンスは必要ありません。 Teams の入手方法の詳細については、「 [Microsoft Teams へのアクセス方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」を参照してください。

## <a name="managing-realwear-devices"></a>RealWear デバイスを管理する

### <a name="microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャー

Android デバイス管理者モードを使用して、RealWear デバイスを管理することができます。 Android Enterprise による管理のサポートには制限があり、現在、デバイスでは Google モバイル サービス (GMS) は利用できません。

- Microsoft エンドポイント マネージャーによる RealWear デバイス管理の詳細については、「[Intune での Android デバイス管理者の登録](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator)」を参照してください。
- ポリシーの詳細については、「[Google モバイル サービスを使用していない環境で Intune を使用する方法](https://docs.microsoft.com/mem/intune/apps/manage-without-gms)」を参照してください。

### <a name="third-party-enterprise-mobility-managers-emms"></a>サードパーティ製 Enterprise Mobility マネージャー (EMM)

サードパーティ製の EMM についてのガイダンスは、「[サポートされている Enterprise Mobility 管理プロバイダー](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)」を参照してください。

## <a name="end-user-content"></a>エンドユーザーのコンテンツ

エンドユーザーの観点からのさらに詳しい情報については、「[Microsoft Teams を RealWear に使用する](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)」を参照してください。
