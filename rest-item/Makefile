test: context install
	@ echo "------------------- Running Tests "
	wct --skip-update-check -l chrome --webserver-port 2121

archive: clean context install
	@ echo "------------------- Creating build folder to be archived "
	mkdir build && mv bower_components build && mkdir build/bower_components/rest-item
	rsync -r * build/bower_components/rest-item --exclude=build
	tar cvf build.tar build

clean:
	@ echo "------------------- Removing previous builds and temporary files "
	rm -fr build build.tar bower_components

install:
	@ echo "------------------- Installing Bower elements "
	rm -fr bower_components
	bower install

context:
	@ echo "------------------- Context "
	@ printf "    Bower version : "
	@ bower -v
	@ printf "    Node version : "
	@ node -v
	@ printf "    User : "
	@ whoami
