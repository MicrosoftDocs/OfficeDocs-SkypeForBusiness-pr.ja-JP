---
title: 会議室Windows更新プログラムをMicrosoft Teamsする
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: 会議室Windows更新プログラムをMicrosoft Teamsする
ms.openlocfilehash: 1a5e665546c00525939585f4655fcdf404e5786f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859994"
---
# <a name="manage-windows-updates"></a>更新Windows管理

Microsoft Teamsルームは、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同Windows更新プログラムと OS ビルドを受け取ります。

Windows更新プログラムは、いくつかの異なる方法で管理できます。

## <a name="hands-off-approach"></a>ハンズオフのアプローチ 
- 更新プログラムは、オフ時間中にWindows更新プログラムから直接ダウンロードしてインストールできます。 構成に変更が行われた場合、これは既定の状態です。
- 遅延不可の更新プログラムは、リリースの 1 日目を自動的にインストールします。 
- 品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。 
- 機能更新。 以下のその他のメモを参照してください。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windowsビジネス向け更新プログラム](/windows/deployment/update/waas-manage-updates-wufb)(GPO または Intune)   
- 更新プログラムは WU または WSUS からダウンロードされますが、KB の元のリリース日を過ぎた遅延が構成されています。 
- 複数の OU またはフィルター処理されたポリシーと組み合わせると、展開 "リング" を作成できます。これにより、管理者は最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。 これにより、たとえば、Microsoft Endpoint Configuration Manager で Windows Updates を管理するオーバーヘッドなしに、展開全体で更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンステストを行えます。
- WSUS と Windowsの更新プログラムを同時に[](/windows/deployment/update/waas-integrate-wufb)構成するには、帯域幅管理とビジネス向け更新プログラムWindowsコントロールの両方が必要です。
- 機能の更新。 以下のその他のメモを参照してください。

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- ビジネス向Windows更新プログラムと同様ですが、各 "リング" または展開全体内の特定の KB を対象とする追加オプションを使用します。 各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストできます。 
- 機能の更新。 以下のその他のメモを参照してください。


### <a name="feature-updates"></a>機能の更新プログラム

品質および延期できない更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft が Microsoft Teams Rooms で特定の更新プログラム機能をテストして検証した後にのみインストールされます。 Semi-Annual チャネル (またはテスト用にシステムが設定されている場合はターゲット) にリリースされた場合や、独自の試行または構成によって手動でプッシュされた場合でも、エンド のブロックが削除されるまでインストールは許可されません。

Microsoft Teamsルーム "アウトオブボックス" は、ハンズオフアプローチを使用して、Windows Update をインストールしたり、デバイスを自動的に再起動したりしません。Windows Update. ただし、システムは更新プログラムをダウンロードし、次回の再起動がインストールされるのを待つ場合があります。 誰かが手動で再起動しない限り、インストールは自動夜間再起動で行う必要があります。 Windows更新プログラムはルーム内で透過的に行う必要があります。更新プログラムによって UI が中断Windows必要があります。

ドメインへの参加を選択した場合は、Microsoft Endpoint Configuration Manager または WSUS を使用し、デバイスが更新プログラムをインストールしたり、営業時間内に再起動を行う可能性があるポリシーやアクションに特に注意してください。 使用中にシステムが再起動したり、UI を使用して Windows更新プログラムに関する通知を受け取った場合は、構成を確認する必要があります。