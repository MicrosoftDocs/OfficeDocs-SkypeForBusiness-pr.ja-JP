---
title: 会議室Windows更新プログラムをMicrosoft Teamsする
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
description: 管理者は、会議室の更新プログラムとWindows機能の更新Windows管理する方法Microsoft Teamsできます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b99e8869ed9fa63a372c6c40d1d0d2be28c019
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503754"
---
# <a name="manage-windows-updates"></a>更新プログラムWindows管理する

Microsoft Teams 会議室は Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) 上で実行され、標準のデスクトップ コンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows更新プログラムは、次のセクションで説明したように管理できます。

## <a name="hands-off-approach"></a>ハンズオフアプローチ 

- 既定では、更新プログラムは、Windowsから直接ダウンロードされ、時間外にインストールされます。
- 遅延不可の更新プログラムは、1 日目のリリースを自動的にインストールします。
- 品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。
- 機能の更新。 次のノートを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows (GPO または Intune) の更新プログラム  

- [Windows for Business のダウンロード](/windows/deployment/update/waas-manage-updates-wufb)
- 更新プログラムは更新プログラムWindows更新プログラム (WSUS) Windows Server Update Servicesからダウンロードされますが、元のリリース日を過ぎた遅延が構成されています。
- 複数の OUs またはフィルター処理されたポリシーを使用してデプロイ "リング" を作成できます。この場合、管理者は、最初に品質更新プログラムをインストールする Teams Rooms デバイスと、後でインストールするデバイスを指定できます。 信頼性とパフォーマンスは、Configuration Manager で更新プログラムを管理するオーバーヘッドなしで、デプロイ全体に更新プログラムを展開する前に、一部のデバイスWindowsテストできます。
- WSUS と Windows for Business の更新プログラムは、帯域幅管理[](/windows/deployment/update/waas-integrate-wufb)とビジネス向け更新プログラムの制御の両方が必要Windows同時に構成できます。
- 機能の更新。 次のノートを参照してください。

## <a name="wsusconfiguration-manager"></a>WSUS/構成マネージャー

- [WSUS/Configuration Manager の](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード
- Update for Business Windowsと同様ですが、各 "リング" またはデプロイ全体内の特定の KB を対象とする追加オプションがあります。 各更新プログラムは、遅延だけに依存するのではなく、個別にデプロイおよびテストできます。
- 機能の更新。 次のノートを参照してください。

### <a name="feature-updates"></a>機能の更新

品質および遅延不可の更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft が Microsoft Teams Rooms で特定の更新プログラム機能をテストして検証した後にのみインストールされます。 更新プログラムが Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムがチャネルに設定されている場合は対象指定)、または手動でプッシュされた場合でも、Microsoft Teams Rooms ではテストされていない更新プログラムのインストールは許可されません。

Microsoft Teamsルームは、ハンズオフアプローチを使用して "アウトオブボックス" で機能します。 Teamsは更新プログラムをダウンロードし、次回の再起動がインストールされるのを待ちます。 誰かが手動で再起動しない限り、インストールは夜間の自動再起動時にのみ実行されます。 Windowsはルーム内で透過的であり、更新プログラムによって通常の操作が中断Windowsがあります。

ドメイン参加デバイスを選択した場合は、Microsoft Endpoint Configuration Manager WSUS を使用できます。 営業時間内にデバイスの更新または強制再起動が発生するポリシーまたはアクションに特に注意してください。 Teamsの間に会議室を再起動したり、使用時間中に UI Windows更新プログラムに関するアラートを送信したりすることはできません。 その動作が発生した場合は、構成を確認します。
