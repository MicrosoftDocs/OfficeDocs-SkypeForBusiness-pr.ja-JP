---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 842831875d3654e5b1d75cdd936d8cc1a6ddf540
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427711"
---
# <a name="manage-windows-updates"></a>Windows の更新プログラムを管理する

Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows 更新プログラムを管理するには、次のような方法があります。

## <a name="hands-off-approach"></a>ハンドオフアプローチ 

- 更新プログラムは、Windows 更新プログラムから直接ダウンロードして、業務時間外にインストールすることができます。 これは既定の構成です。
- 無遅延更新プログラムによって、リリース日が自動的にインストールされます。
- 品質更新プログラムとドライバーのダウンロードとインストールが自動的に行われます。
- 機能の更新。 以下のメモを参照してください。

## <a name="windows-updates-for-business-gpo-or-intune"></a>ビジネス向け Windows 更新プログラム (GPO または Intune)  

- 一般[法人向けダウンロード用の Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- 更新プログラムは WU または WSUS からダウンロードされますが、KB の最初のリリース日よりも遅延が構成されています。
- 複数の OU またはフィルター処理されたポリシーと共に使用することで、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールすることを指定できます。 これにより、システムのサブセットに対する信頼性とパフォーマンスのテストを行うことができます。これにより、SCCM での Windows の更新プログラムの管理に伴うオーバーヘッドを生じることなく、展開全体で更新プログラムをロールアウトすることができます。
- ビジネス向けの帯域幅管理と Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。
- 機能の更新。 以下のメモを参照してください。

## <a name="wsussccm"></a>WSUS/SCCM

- [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)のダウンロード
- 一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。 各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。
- 機能の更新。 以下のメモを参照してください。

### <a name="feature-updates"></a>機能の更新プログラム

品質と不確認可能な更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。 半期チャネルに更新プログラムがリリースされている場合 (またはテスト用にシステムを設定している場合)、または手動でプッシュした場合でも、Microsoft Room Systems デバイスでは、テストされていない更新プログラムをインストールすることはできません。

ハンズオフアプローチを使用した Microsoft Teams の会議室では、windows update をインストールしたり、Windows Update 用のデバイスを自動的に再起動したりすることはありません。 システムによって更新プログラムがダウンロードされ、次に再起動するまで待機してからインストールされることがあります。 手動で再起動しない限り、自動夜間再起動時にインストールが行われます。 Windows の更新プログラムは、会議室では透過的である必要があります。 UI は Windows 更新プログラムによって中断されることはありません。

ドメインに参加しているデバイスを選択する場合は、SCCM または WSUS を使用します。 デバイスで更新プログラムをインストールしたり、業務時間中に再起動を強制したりする可能性のあるポリシーまたはアクションには、特別な注意を払ってください。 展開内のシステムは使用中に再起動しないようにする必要があります。または、使用時間中に UI を介した Windows 更新についての通知で、動作が発生した場合は構成を確認します。