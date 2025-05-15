# create and flash an img

* create img
    `dd if=dev/sdX of=img bs=4M`

- flash img
	`dd if=img of=/dev/sdX bs=4M`

- shrink img
	`sudo raspbian-shrink old-img new-img`

* zip img
    `sudo tar`
