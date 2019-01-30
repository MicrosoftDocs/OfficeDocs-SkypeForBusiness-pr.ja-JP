---
title: Lync 2010 クライアント コンピューターの個人用連絡先ストアを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: は、レガシ クライアントで使用されている個人用連絡先ストアを構成します。'
ms.openlocfilehash: b817ae3c7e4e8d54a06d497d91ca83d2b8715e8d
ms.sourcegitcommit: 5cf9b45ad87aebfd46d3f1f757786c01804143ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "29635707"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 クライアント コンピューターの個人用連絡先ストアを構成します。
  
ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 の Skype を統合する場合は、クライアントによって使用される個人用の連絡先ストアを構成してください。 具体的には、Skype をビジネスで個人の連絡先ストアとして Exchange を使用し、同時に、ユーザーは、その判断をオーバーライドできないことを確認しますを構成する必要があります。 そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。
  
> [!NOTE]
> 次の手順は、Lync 2010 クライアントを使用するクライアントに必要なまたはそれ以前ではのみです。 Lync 2013 クライアントとビジネス クライアント用のすべての Skype は、連絡先ストアの設定を上書きすることはありません。
  
1 台のコンピューターでこの値を構成するには、次の手順を実行します。
  
1. クライアント コンピューターで [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
2. [**ファイル名を指定して実行**] ダイアログ ボックスで「regedit」と入力して、Enter キーを押します。
3. レジストリ エディターで、[**HKEY_LOCAL_MACHINE**]、[**Software**]、[**Policies**]、[**Microsoft**]、[**Communicator**] の順に展開します。
4. [**Communicator**] を右クリックし、[**新規**] をポイントし、[**DWORD (32 ビット) 値**] をクリックします。
5. 新しい値を作成した後に「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。
6. PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 Windows 10 でこれを行う方法の詳細については、[グループ ポリシー オブジェクトを作成する](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)資料を参照してください。
  