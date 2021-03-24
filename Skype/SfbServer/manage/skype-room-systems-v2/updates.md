---
title: Microsoft Teams 会議室の Windows 更新プログラムを管理する
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
description: Microsoft Teams 会議室の Windows 更新プログラムを管理する
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103203"
---
# <a name="manage-windows-updates"></a>Windows 更新プログラムの管理

Microsoft Teams Rooms は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows の更新プログラムは、次に示すいくつかの方法で管理できます。

## <a name="hands-off-approach"></a>ハンズオフのアプローチ 
- 更新プログラムは、Windows の更新プログラムから直接自動的にダウンロードし、オフ時間にインストールできます。 構成に変更が行われた場合、これは既定の状態です。
- 遅延不可の更新プログラムは、リリースの 1 日目を自動的にインストールします。 
- 品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。 
- 機能更新。 以下のその他のメモを参照してください。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO または Intune)   
- 更新プログラムは WU または WSUS からダウンロードされますが、KB の元のリリース日を過ぎた遅延が構成されています。 
- 複数の OU またはフィルター処理されたポリシーと組み合わせると、展開 "リング" を作成できます。これにより、管理者は最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。 これにより、たとえば Microsoft Endpoint Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドなしに、展開全体で更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンステストを行えます。
- 帯域幅管理と Windows Updates for [](/windows/deployment/update/waas-integrate-wufb) Business が提供するコントロールの両方が必要な場合は、WSUS と Windows Updates for Business を同時に構成できます。
- 機能の更新。 以下のその他のメモを参照してください。

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Windows Update for Business と同様ですが、各 "リング" または展開全体の中で特定の KB をターゲットに設定するオプションが追加されています。 各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストできます。 
- 機能の更新。 以下のその他のメモを参照してください。


### <a name="feature-updates"></a>機能の更新プログラム

品質および延期不可の更新プログラムとは異なり、Windows 10 の "機能更新プログラム" (主要な OS リリース) は、Microsoft Teams Rooms で特定の更新プログラムの機能をテストして検証した後にのみインストールされます。 Semi-Annual チャネル (またはテスト用にシステムが設定されている場合はターゲット) にリリースされた場合や、独自の試行または構成によって手動でプッシュされた場合でも、エンド のブロックが削除されるまでインストールは許可されません。

Microsoft Teams Room "アウトオブボックス" は、ハンズオフアプローチを使用して、Windows Update をインストールしたり、Windows Update のためにデバイスを自動的に再起動したりしません。 ただし、システムは更新プログラムをダウンロードし、次回の再起動がインストールされるのを待つ場合があります。 誰かが手動で再起動しない限り、インストールは自動夜間再起動で行う必要があります。 Windows の更新プログラムは、ルーム内で透過的である必要があります。UI は Windows 更新プログラムによって中断される必要があります。

ドメインへの参加を選択した場合は、Microsoft Endpoint Configuration Manager または WSUS を使用し、デバイスが更新プログラムをインストールしたり、営業時間内に再起動を行う可能性があるポリシーやアクションに特に注意してください。 UI を使用して Windows 更新プログラムに関する警告を表示したり、使用中にシステムを再起動している場合は、構成を確認する必要があります。