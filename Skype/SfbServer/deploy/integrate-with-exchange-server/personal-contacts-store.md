---
title: Lync 2010 クライアントコンピューターで個人用連絡先ストアを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: レガシクライアントで使用される個人用連絡先ストアを構成します。'
ms.openlocfilehash: a80af6ca575b53e5a2b8f77a109fd6929f0db704
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797028"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 クライアントコンピューターで個人用連絡先ストアを構成する
  
Skype for Business Server 2015 と Exchange Server 2016、または Exchange Server 2013 を統合する場合は、クライアントで使用する個人用連絡先ストアを構成する必要があります。 特に、Skype for Business が個人の連絡先ストアとして Exchange を使用するように構成し、同時にユーザーがその決定を上書きできないようにする必要があります。 そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。
  
> [!NOTE]
> 次の手順は、Lync 2010 クライアントまたはそれ以前のバージョンを使用しているクライアントに対してのみ必要です。 Lync 2013 クライアントとすべての Skype for Business クライアントには、連絡先ストアの設定を上書きするオプションはありません。
  
1 台のコンピューターでこの値を構成するには、次の手順を実行します。
  
1. クライアント コンピューターで [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
2. [**ファイル名を指定して実行**] ダイアログ ボックスで「regedit」と入力して、Enter キーを押します。
3. レジストリ エディターで、[**HKEY_LOCAL_MACHINE**]、[**Software**]、[**Policies**]、[**Microsoft**]、[**Communicator**] の順に展開します。
4. [**Communicator**] を右クリックし、[**新規**] をポイントし、[**DWORD (32 ビット) 値**] をクリックします。
5. 新しい値を作成した後に「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。
6. PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 Windows 10 での操作の詳細については、「[グループポリシーオブジェクトを作成する](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)」を参照してください。
  
