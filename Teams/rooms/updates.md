---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
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
description: 管理者は、Microsoft Teams ルームの Windows 更新プログラムと Windows の機能更新プログラムを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117365"
---
# <a name="manage-windows-updates"></a>Windows 更新プログラムを管理する

Microsoft Teams Rooms は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップ コンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows 更新プログラムは、次のセクションで説明したように管理できます。

## <a name="hands-off-approach"></a>ハンズオフ アプローチ 

- 既定では、更新プログラムは Windows 更新プログラムから直接自動的にダウンロードされ、営業時間外にインストールされます。
- 遅延提供不可の更新プログラムは、リリースの 1 日目に自動的にインストールされます。
- 品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。
- 機能の更新。 次のノートを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>ビジネス向け Windows 更新プログラム (GPO または Intune)  

- [ビジネス向け Windows 更新プログラムの](/windows/deployment/update/waas-manage-updates-wufb) ダウンロード
- 更新プログラムは Windows Update または WSUS からダウンロードされますが、元のリリース日を過ぎた遅延が構成されています。
- 複数の OUs またはフィルター処理されたポリシーを使用して展開 "リング" を作成できます。このリングでは、最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。 Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドなしで、展開全体に更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンスをテストできます。
- 帯域幅管理とビジネス向け Windows [](/windows/deployment/update/waas-integrate-wufb) Updates の制御の両方が必要な場合は、WSUS と Windows Updates for Business を同時に構成できます。
- 機能の更新。 次のノートを参照してください。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager の](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード
- Windows Update for Business と同様ですが、各 "リング" 内または展開全体内の特定の KB を対象とする追加オプションがあります。 各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストすることができます。
- 機能の更新。 次のノートを参照してください。

### <a name="feature-updates"></a>機能の更新

品質および非延期更新プログラムとは異なり、Windows 10 の "機能更新プログラム" (メジャー OS リリース) は、Microsoft Teams Rooms で特定の更新プログラム機能をテストして検証した後にのみインストールされます。 更新プログラムが Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムをそのチャネルに設定している場合は対象指定済み) または手動でプッシュされた場合でも、Microsoft Room Systems デバイスでは、テストされていない更新プログラムのインストールは許可されません。

Microsoft Teams Rooms は、ハンズオフ アプローチで "アウト オブ ボックス" 機能し、Windows Update をインストールしたり、Windows Update のデバイスを自動的に再起動したりしません。 システムは更新プログラムをダウンロードし、次に再起動してインストールされるのを待ちます。 手動で再起動しない限り、インストールは夜間自動再起動でのみ実行されます。 Windows 更新プログラムはルーム内で透明にする必要があります。また、Windows 更新プログラムによって通常の操作が中断されるのは絶対にありません。

ドメイン参加デバイスを選ぶ場合は、Microsoft Endpoint Configuration Manager または WSUS を使用します。 営業時間内にデバイスが更新または強制的に再起動されるポリシーやアクションには特に注意してください。 使用時間中に展開内のシステムを再起動したり、UI を使用して Windows 更新プログラムに関する警告を表示したりし、その動作が発生した場合は構成を確認してください。