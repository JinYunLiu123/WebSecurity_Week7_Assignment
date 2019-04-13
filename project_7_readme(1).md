# Project 7 - WordPress Pentesting

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability: Pupload Same Origin Method Execution (SOME)
  - [ ] Summary: 
    - Vulnerability types: SOME, XSS
    - Tested in version: 4.2
    - Fixed in version:  4.2.13
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
			1. Go to any post.
			2. Paste the following as a comment in text.
			
			  <button onclick = "fire()">Click<button>
			  <script>
			  function fire() {
			    open('javascript:alert(1)');
			  }
			  </script>
			  
			3. Click the button.
			4. Alert(1) will pop up.
			
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)
2. (Required) Vulnerability: Authenticated Stored Cross-Site Scripting via Image Filename
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version:  4.2.2
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
			1. Rename the image file to img src= a onerror = alert(document.cookie)
			2. Upload the image to WordPress
			3. Create a post and add image to posts
			4. Change the attachment displat to "Attachment page"
  - [ ] Affected source code:
    - [Link 2](https://sumofpwn.nl/advisory/2016/persistent_cross_site_scripting_vulnerability_in_wordpress_due_to_unsafe_processing_of_file_names.html)
3. (Required) Vulnerability: Authenticated Stored Cross-Site Scripting in YouTube URL Embeds
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.0-4.7.2
    - Fixed in version:  4.2.13
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
			1. Login as a user with the ability to create new posts
			2. In the post body add the followin gyoutube embed code:
			
			[embed src='https://youtube.com/embed/123\x3csvgonload=alert(1)\x3e'][/embed]
  - [ ] Affected source code:
    - [Link 3](https://klikki.fi/adv/wordpress2.html)


## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
