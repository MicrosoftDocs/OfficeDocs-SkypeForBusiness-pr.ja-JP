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
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 2fc96118b70ff7c15e7bde02fdcd048c07581ad3
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827915"
---
# <a name="manage-windows-updates"></a>Windows の更新プログラムを管理する

Microsoft Teams のルームは、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準のデスクトップコンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows 更新プログラムは、次のセクションで説明するように管理できます。

## <a name="hands-off-approach"></a>ハンドオフアプローチ 

- 既定では、更新プログラムは Windows 更新プログラムから自動的にダウンロードされ、オフ時間中にインストールされます。
- 無遅延更新プログラムによって、リリース日が自動的にインストールされます。
- 品質更新プログラムとドライバーのダウンロードとインストールが自動的に行われます。
- 機能の更新。 以下のメモを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>ビジネス向け Windows 更新プログラム (GPO または Intune)  

- 一般[法人向けダウンロード用の Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- 更新プログラムは、Windows Update または WSUS からダウンロードされますが、最初のリリース日以降の遅延は構成されています。
- 複数の Ou またはフィルター処理されたポリシーを使用して、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールすることを指定できます。 信頼性とパフォーマンスは、構成マネージャーでの Windows 更新プログラムの管理ではなく、展開全体で更新プログラムをロールアウトする前に、システムのサブセットに対してテストすることができます。
- ビジネス向けの帯域幅管理と Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。
- 機能の更新。 以下のメモを参照してください。

## <a name="wsusconfiguration-manager"></a>WSUS/構成マネージャー

- [WSUS/構成マネージャー](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)のダウンロード
- 一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。 各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。
- 機能の更新。 以下のメモを参照してください。

### <a name="feature-updates"></a>機能の更新プログラム

品質と不確認可能な更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。 半期チャネルに更新プログラムがリリースされている場合 (またはテスト用にシステムを設定している場合)、または手動でプッシュした場合でも、Microsoft Room Systems デバイスでは、テストされていない更新プログラムをインストールすることはできません。

Microsoft Teams の会議機能は、ハンズオフアプローチを備えた、Windows Update をインストールしたり、Windows Update 用のデバイスを自動的に再起動したりすることはありません。 システムは更新プログラムをダウンロードして、次に再起動するまで待ってからインストールします。 手動で再起動しない限り、インストールは自動夜間の再起動としてのみ行われます。 Windows の更新プログラムはルームで透過的である必要があります。また、通常の操作は Windows 更新プログラムによって中断されることはありません。

[Domain join devices] を選んだ場合は、Microsoft Endpoint Configuration Manager または WSUS を使用します。 デバイスの更新、または営業時間中に再起動が行われるポリシーやアクションには、特別な注意を払ってください。 展開内のシステムは使用中に再起動しないようにする必要があります。または、使用時間中に UI を介した Windows 更新についての通知で、動作が発生した場合は構成を確認します。