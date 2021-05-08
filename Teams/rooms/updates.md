---
title: 更新プログラムWindows管理Microsoft Teams ミーティング
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 管理者は、更新プログラムを管理し、Windows更新プログラムWindows更新プログラムを管理する方法についてMicrosoft Teams ミーティング。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117365"
---
# <a name="manage-windows-updates"></a>更新プログラムWindows管理する

Microsoft Teams ミーティング IoT または Windows 10 Enterprise Windows 10 Enterprise (VL) で実行され、標準のデスクトップ コンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows更新プログラムは、次のセクションで説明したように管理できます。

## <a name="hands-off-approach"></a>ハンズオフアプローチ 

- 既定では、更新プログラムは、Windowsから直接ダウンロードされ、時間外にインストールされます。
- 遅延不可の更新プログラムは、1 日目のリリースを自動的にインストールします。
- 品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。
- 機能の更新。 次のノートを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windowsビジネス向け更新プログラム (GPO または Intune)  

- [Windows for Business の更新プログラムの](/windows/deployment/update/waas-manage-updates-wufb)ダウンロード
- 更新プログラムは更新プログラムWindows WSUS からダウンロードされますが、元のリリース日を過ぎた遅延が構成されています。
- 複数の OUs またはフィルター処理されたポリシーを使用してデプロイ "リング" を作成できます。この場合、管理者は、品質更新プログラムを最初にインストールするデバイスと、後でインストールするデバイスを指定できます。 信頼性とパフォーマンスは、Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドなしに、デプロイ全体に更新プログラムを展開する前に、一部のシステムでテストできます。
- WSUS と Windows for Business の[](/windows/deployment/update/waas-integrate-wufb)更新プログラムは、帯域幅管理とビジネス向け更新プログラムの制御の両方が必要な場合Windows同時に構成できます。
- 機能の更新。 次のノートを参照してください。

## <a name="wsusconfiguration-manager"></a>WSUS/構成マネージャー

- [WSUS/Configuration Manager の](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード
- ビジネス向Windows更新プログラムと同様ですが、各 "リング" またはデプロイ全体内の特定の KB を対象とする追加オプションがあります。 各更新プログラムは、遅延だけに依存するのではなく、個別にデプロイおよびテストできます。
- 機能の更新。 次のノートを参照してください。

### <a name="feature-updates"></a>機能の更新

品質および遅延不可の更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft が Microsoft Teams ミーティング で特定の更新プログラム機能をテストして検証した後にのみインストールされます。 更新プログラムが Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムがチャネルに設定されている場合は対象指定済み) または手動でプッシュされた場合でも、Microsoft Room Systems デバイスはテストされていない更新プログラムのインストールを許可されません。

Microsoft Teams ミーティングはハンズオフアプローチで "アウトオブボックス" 機能を提供し、Windows Update をインストールしたり、Windows Update のデバイスを自動的に再起動したりしません。 システムは更新プログラムをダウンロードし、次回の再起動がインストールされるのを待ちます。 誰かが手動で再起動しない限り、インストールは夜間の自動再起動時にのみ行います。 Windows更新はルーム内で透過的に行う必要があります。また、通常の操作が更新プログラムによって中断Windows必要があります。

ドメイン参加デバイスを選択する場合は、Microsoft Endpoint Configuration Manager または WSUS を使用します。 営業時間内にデバイスの更新または強制再起動が発生するポリシーまたはアクションに特に注意してください。 デプロイ内のシステムは、使用中に再起動したり、使用時間中に UI Windows 更新プログラムに関するアラートを送信したりし、その動作が発生した場合は構成を確認してください。