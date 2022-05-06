---
title: Microsoft Teams RoomsのWindows更新プログラムを管理する
ms.author: czawideh
author: cazawideh
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
ms.assetid: ''
description: 管理者は、Microsoft Teams RoomsのWindows更新プログラムとWindows機能更新プログラムを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b99e8869ed9fa63a372c6c40d1d0d2be28c019
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503754"
---
# <a name="manage-windows-updates"></a>Windows更新プログラムの管理

Microsoft Teams Roomsは、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップ コンピューターと同じWindows更新プログラムと OS ビルドを受け取ります。

Windows更新プログラムは、次のセクションで説明するように管理できます。

## <a name="hands-off-approach"></a>ハンズオフ アプローチ 

- 既定では、更新プログラムはWindows更新プログラムから直接ダウンロードされ、時間外に自動的にインストールされます。
- 延期できない更新プログラムでは、リリースの 1 日目が自動的にインストールされます。
- 品質更新プログラムとドライバーは、1 日目に自動的にダウンロードしてインストールします。
- 機能の更新プログラム。 次のノートを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows ビジネス向け更新プログラム (GPO またはIntune)  

- [Windows ビジネス向け更新プログラムの](/windows/deployment/update/waas-manage-updates-wufb)ダウンロード
- 更新プログラムは、Windows UpdateまたはWindows Server Update Services (WSUS) からダウンロードされますが、元のリリース日を過ぎて遅延が構成されています。
- 複数の OU またはフィルター処理されたポリシーを使用して、管理者が品質更新プログラムを最初にインストールするTeams Roomsデバイスと後でインストールするデバイスを指定できる展開 "リング" を作成できます。 Configuration ManagerでWindows更新プログラムを管理するオーバーヘッドなしで、デプロイ全体で更新プログラムをロールアウトする前に、デバイスのサブセットで信頼性とパフォーマンスをテストできます。
- 帯域幅管理とビジネス向け更新プログラムの制御Windows両方[を](/windows/deployment/update/waas-integrate-wufb)提供する場合は、ビジネス向け WSUS とWindowsの更新プログラムを同時に構成できます。
- 機能の更新プログラム。 次のノートを参照してください。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード
- ビジネス向けのWindows Updateとよく似ていますが、各 "リング" 内またはデプロイ全体で特定の KB をターゲットにするための追加オプションがあります。 各更新プログラムは、遅延のみに依存するのではなく、個別に展開してテストできます。
- 機能の更新プログラム。 次のノートを参照してください。

### <a name="feature-updates"></a>機能の更新

品質更新プログラムと非延期更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft がMicrosoft Teams Roomsを使用して特定の更新プログラム機能をテストして検証した後にのみインストールされます。 更新プログラムがSemi-Annual チャネルにリリースされた場合 (またはテスト用にシステムがそのチャネルに設定されている場合はターゲットに設定されている場合)、手動でプッシュされた場合でも、Microsoft Teams Rooms未テストの更新プログラムのインストールは許可されません。

Microsoft Teams Rooms、ハンズオフアプローチを使用して "すぐに使える" 関数を使用します。 Teams Rooms更新プログラムをダウンロードし、次の再起動がインストールされるまで待ちます。 誰かが手動で再起動しない限り、インストールは夜間の自動再起動でのみ行われます。 Windows更新プログラムは室内で透過的である必要があり、通常の操作はWindows更新プログラムによって中断しないでください。

デバイスにドメイン参加することを選択した場合は、Microsoft Endpoint Configuration Managerまたは WSUS を使用できます。 営業時間中にデバイスの更新や強制的な再起動が発生するポリシーやアクションに特に注意してください。 Teams Roomsは、使用中に再起動したり、使用時間中に UI 経由で更新Windowsに関するアラートを表示したりしないでください。 その動作が発生した場合は、構成を確認します。
