---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832877"
---
# <a name="manage-windows-updates"></a>Windows 更新プログラムの管理

Microsoft Teams Rooms は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows 更新プログラムは、いくつかの異なる方法で管理できます。

## <a name="hands-off-approach"></a>ハンズオフアプローチ 
- 更新プログラムは、Windows 更新プログラムから直接自動的にダウンロードし、オフ時間にインストールできます。 構成に変更が行われた場合、これは既定の状態です。
- 延期不可の更新プログラムは、リリースの 1 日目を自動的にインストールします。 
- 品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。 
- 機能更新。 以下の追加のメモを参照してください。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO または Intune)   
- 更新プログラムは WU または WSUS からダウンロードされますが、KB の元のリリース日を過ぎた遅延が構成されています。 
- 複数の OU またはフィルター処理されたポリシーと組み合わせると、展開 "リング" を作成できます。このリングでは、管理者は、最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。 これにより、Microsoft Endpoint Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドを発生することなく、展開全体で更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンスをテストできます。
- 帯域幅管理と Windows Updates for [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) Business の制御の両方が必要な場合は、WSUS と Windows Updates for Business を同時に構成できます。
- 機能更新プログラム。 以下の追加のメモを参照してください。

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Windows Update for Business と同様ですが、各 "リング" 内または展開全体内の特定の KB を対象とする追加オプションがあります。 各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストできます。 
- 機能更新プログラム。 以下の追加のメモを参照してください。


### <a name="feature-updates"></a>機能の更新プログラム

品質更新プログラムや延期不可の更新プログラムとは異なり、Windows 10 の "機能更新プログラム" (メジャー OS リリース) は、Microsoft Teams Rooms で特定の更新プログラム機能をテストして検証した後にのみインストールされます。 Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムをそのチャネルに設定している場合は対象指定)、または独自の試行または構成によって手動でプッシュされた場合でも、エンドのブロックが削除されるまでインストールは許可されません。

Microsoft Teams Room "out-of-box"は、ハンズオフ アプローチを使用して、Windows Update をインストールしたり、Windows Update のためにデバイスを自動的に再起動したりしません。 ただし、システムは更新プログラムをダウンロードし、次回の再起動によってインストールされるのを待つ場合があります。 ユーザーが手動で再起動しない限り、インストールは夜間の自動再起動時に行う必要があります。 Windows 更新プログラムは、ルーム内で透過的である必要があります。UI は Windows 更新プログラムによって中断されません。

ドメイン参加を選択する場合は、Microsoft Endpoint Configuration Manager または WSUS を使用し、デバイスで更新プログラムをインストールしたり、業務時間中に再起動を実行したりする可能性があるポリシーやアクションに特に注意してください。 展開内のシステムが、使用中に再起動したり、UI を使用して Windows 更新プログラムに関する警告を表示したりしている場合は、構成を確認する必要があります。
