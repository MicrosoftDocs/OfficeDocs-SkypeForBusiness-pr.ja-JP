---
title: Microsoft Teams Roomsの Windows 更新を管理する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: 管理、Microsoft Teams Rooms用の Windows 更新および Windows 機能更新プログラムを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272182"
---
# <a name="manage-windows-updates"></a>Windows 更新を管理する

Microsoft Teams Roomsは、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップ コンピューターと同じ Windows 更新 および OS ビルドを受け取ります。

Windows 更新は、次のセクションで説明するように管理できます。

## <a name="hands-off-approach"></a>ハンズオフ アプローチ 

- 既定では、更新プログラムは Windows 更新から直接ダウンロードされ、時間外に自動的にインストールされます。
- 延期できない更新、リリースの 1 日目に自動的にインストールされます。
- 品質更新とドライバーは、自動的にダウンロードしてインストールします。
- 機能更新。 次のノートを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows 更新 for Business (GPO またはIntune)  

- [Windows 更新 for Business の](/windows/deployment/update/waas-manage-updates-wufb)ダウンロード
- 更新はWindows UpdateまたはWindows Server Update Services (WSUS) からダウンロードされますが、元のリリース日を過ぎて遅延が構成されています。
- 複数の OU またはフィルター選択されたポリシーを使用して、展開 "リング" を作成できます。管理者は、最初に品質更新をインストールするTeams Roomsデバイスと、後でインストールするデバイスを指定できます。 信頼性とパフォーマンスは、Configuration Managerで Windows 更新を管理するオーバーヘッドなしで、展開全体で更新プログラムをロールアウトする前に、デバイスのサブセットでテストできます。
- WSUS と Windows 更新 for Business は、帯域幅管理と Windows 更新 for Business が提供する制御の両方が必要な場合に[同時に構成](/windows/deployment/update/waas-integrate-wufb)できます。
- 機能の更新プログラム。 次のノートを参照してください。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード
- ビジネス向けのWindows Updateとよく似ていますが、各 "リング" 内またはデプロイ全体で特定の KB をターゲットにするための追加オプションがあります。 各更新プログラムは、遅延のみに依存するのではなく、個別に展開してテストできます。
- 機能の更新プログラム。 次のノートを参照してください。

### <a name="feature-updates"></a>機能の更新

品質更新プログラムと非延期更新プログラムとは異なり、Windows 10 "機能更新" (メジャー OS リリース) は、Microsoft がMicrosoft Teams Roomsを使用して特定の更新プログラム機能をテストして検証した後にのみインストールされます。 更新プログラムがSemi-Annual チャネルにリリースされた場合 (またはテスト用にシステムがそのチャネルに設定されている場合はターゲットに設定されている場合)、手動でプッシュされた場合でも、Microsoft Teams Rooms未テストの更新プログラムのインストールは許可されません。

Microsoft Teams Rooms、ハンズオフアプローチを使用して "すぐに使える" 関数を使用します。 Teams Rooms更新プログラムをダウンロードし、次の再起動がインストールされるまで待ちます。 誰かが手動で再起動しない限り、インストールは夜間の自動再起動でのみ行われます。 Windows 更新は室内で透過的である必要があり、Windows 更新によって通常の操作を中断しないでください。

デバイスにドメイン参加することを選択した場合は、Microsoft Endpoint Configuration Managerまたは WSUS を使用できます。 営業時間中にデバイスの更新や強制的な再起動が発生するポリシーやアクションに特に注意してください。 Teams Roomsは、使用中に再起動したり、使用時間中に UI 経由で Windows 更新に関するアラートを表示したりしないでください。 その動作が発生した場合は、構成を確認します。
